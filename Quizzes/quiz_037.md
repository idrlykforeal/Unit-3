# Code
```.py
class CompundInterest:
    def __init__(self, principal, rate, num_of_years):
        self.principal = principal
        self.rate = rate
        self.num_of_years = num_of_years

    def compound_interest_calculator(self):
        # round to 2 decimal places
        return round(self.principal * (1 + self.rate) ** self.num_of_years, 2)


# provide methods to set principal, rate, and years, and calculate_interest method that gets the compound interest by calling calculate method of the object

class AccountingProgram:
    def __init__(self):
        self.compound = CompundInterest(0,0,0)
    def set_principal(self,principal):
        if principal>0:
            self.compound.principal = principal
        else:
            raise ValueError("Principal should be greater than zero")
    def set_rate(self,rate):
        if rate>0:
            self.compound.rate = rate
        else:
            raise ValueError("Interest rate should be greater than zero")
    def set_years(self,years):
        if years>0:
            self.compound.num_of_years = years
        else:
            raise ValueError("Years should be greater than zero")
    def calculate_interest(self):
        return self.compound.compound_interest_calculator()
```

# Test
<img width="686" alt="quiz_037" src="https://user-images.githubusercontent.com/100017195/213068725-11752a64-362b-4455-ad11-e4b0d436f2ea.png">

