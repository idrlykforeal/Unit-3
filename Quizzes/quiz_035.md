# code
```.py
class Account:
    def __init__(self):
        self.balance = 0
        self.holder_name = ""
        self.holder_email = ""
        self.number = [900,11324,5]

    def get_account_no(self)->str:
        return f"{self.number[0]}-{self.number[1]}-{self.number[2]}"

    def set_holder_name(self, name:str)->str:
        if not isinstance(name,str):
            raise ValueError("Name must be a string")
        else:
            self.holder_name = name
        return f"Holder's name set to {name}"

    def set_holder_email(self, email:str)->str:
        if not isinstance(email,str):
            raise ValueError("Email must be a string")

        else:
            self.holder_email = email
        return f"Holder's email set to {email}"

    def get_balance(self)->int:
        return self.balance

    def deposit(self, amount:int)->int:
        self.balance += amount
        return f"New balance: {self.balance} USD"
```

# test pass
<img width="790" alt="Screen Shot 2023-01-26 at 9 13 06 PM" src="https://user-images.githubusercontent.com/100017195/214832800-ea609f6a-f000-4f24-8334-695d85dca0d3.png">
