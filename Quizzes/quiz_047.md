# python

## update

```.py
def update(self):

        #This function updates all the labels in the form using the base salary and the percentage
        # Pseudocode
        # 1- get the base salary from the GUI
        base = self.root.ids.base.text
        hash = ""
        # 2- if base salary define total=int(base) and an empty string to store build a hash (for_hash="") if no base then end the function
        test_field_ids = [ 'health', 'pension', 'income_tax','inhabitant']
        if base !="":
            total = int(base)
            hash += f"base{total}"

            for i in test_field_ids:
                value = self.root.ids[i].text
                if value !="":
                    new_value=f"{int(value)*int(base)/100} JPY"
                    total-= int(value)*int(base)/100
                    hash+=f"{i}{value}"
                else: new_value="JPY"
                label_id=f"{i}_label"
                self.root.ids[label_id].text= new_value

            hash += f"total{int(total)}"
            self.root.ids.salary_label.text = f"{total} JPY"
            hashed = encrypt_pswd(hash)
            self.hash = hashed
            self.root.ids.hash.text = hashed[-50:]
```

## save

```.py
def save(self):
        def save(self):
            base_widget = self.root.ids.base
            base = base_widget.text.strip()
            values = {
                "base": self.root.ids.base_label.text.strip()[:-4],
                "inhabitant": self.root.ids.inhabitant_label.text.strip()[:-4],
                "income_tax": self.root.ids.income_tax_label.text.strip()[:-4],
                "pension": self.root.ids.pension_label.text.strip()[:-4],
                "health": self.root.ids.health_label.text.strip()[:-4],
                "salary": self.root.ids.salary_label.text.strip()[:-4],
                "hash": self.hash,
            }

            query = "INSERT INTO payments (base, inhabitant, income_tax, pension, health, total, hash) VALUES (?, ?, ?, ?, ?, ?, ?)"
            db = database_worker("payments.db")
            try:
                db.cursor.execute(query, [values[key] for key in values.keys()])
                db.connection.commit()
                self.root.ids.hash_label.text = "Payment saved"
            except Exception as e:
                print(f"Error saving payment: {e}")
            finally:
                db.close()
        self.root.ids.hash.text = f"Payment saved"

```

## checking hashed transactions (HL)

```.py
def check(self):
        conn = sqlite3.connect('payments.db')
        cursor = conn.cursor()
        cursor.execute("SELECT * FROM payments")
        rows=cursor.fetchall()

        for row in rows:
            get_hashed = encrypt_pswd(f"base{row[1]}inhabitant{row[2]}income_tax{row[3]}pension{row[4]}health{row[5]}total{row[6]}")
            if get_hashed[-50:] == row[7]:
                print("OK")
            else:
                print(f"Error in id: {row[0]}")
```


# evidence

<img width="912" alt="image" src="https://user-images.githubusercontent.com/100017195/224213086-05184fda-3d7b-48c3-b404-67b8ceaffb5f.png">
