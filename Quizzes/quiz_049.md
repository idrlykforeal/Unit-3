# code

```.py
import sqlite3

from secure_password import encrypt_pswd, check_pswd


class database_worker:
    def __init__(self, name):
        self.connection = sqlite3.connect(name)
        self.cursor = self.connection.cursor()

    def search(self, query):
        result = self.cursor.execute(query).fetchall()
        return result

    def run_save(self, query):
        self.cursor.execute(query)
        self.connection.commit()

    def close(self):
        self.connection.close()


x= database_worker("bitcoin_exchange.db")

query = "SELECT * from ledger"
result = x.search(query)
green = "\033[0;32m"
red = "\33[0;31m"
end_code = "\033[00m"
total = 0

for row in result:
    unhashed = f"id {row[0]},sender_id {row[1]},receiver_id {row[2]},amount {row[3]}"
    hashed= row[4]

    equal=check_pswd(hashed_pswd=hashed, user_pswd=unhashed)
    if equal:
        msg=f"{green}Tx({row[0]})Signature Matches{end_code}"
        total += row[3]
    else:
        msg=f"{red}Tx({row[0]})Error Signature{end_code}"
    print(msg)

print(f"Total amount of bitcoin in the ledger is {total}")

```

# proof
<img width="505" alt="Screenshot 2023-02-24 at 3 08 18 PM" src="https://user-images.githubusercontent.com/100017195/221105021-252c9fb8-d42d-4d25-a3b7-a18d702b33f5.png">
