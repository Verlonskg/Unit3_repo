# Quiz 034

## Code
```.py
class CompoundInterest:

    def __init__(self, principal: str, rate: int, year: int):
        self.principal = principal
        self.rate = rate
        self.year = year

    def compound_interest_calculator(self):
        principal = self.principal
        rate = self.rate
        year = self.year
        total = principal * (1 + rate) ** year
        return round(total, 2)

class AccountingProgram:

    def __init__(self):
        self.compound = CompoundInterest(0, 0, 0)

    def set_principal(self, new_compound):
        if new_compound > 0:
            self.compound.principal = new_compound
        else:
            raise ValueError("Principal should be greater than zero")

    def set_rate(self, new_rate):
        if new_rate > 0:
            self.compound.rate = new_rate
        else:
            raise ValueError("Interest rate should be greater than zero")

    def set_years(self, year):
        if year > 0:
            self.compound.year = year
        else:
            raise ValueError("Years should be greater than zero")

    def calculate_interest(self):
        return self.compound.compound_interest_calculator()

```
## Test Case 
```.py 
import pytest
from quiz_037 import AccountingProgram

def test_calculate_interest():
    program = AccountingProgram()
    program.set_principal(1000)
    program.set_rate(0.05)
    program.set_years(10)
    interest = program.calculate_interest()
    assert interest == 1628.89

def test_principal_validation():
    program = AccountingProgram()
    with pytest.raises(ValueError) as err:
        program.set_principal(-1000)
    assert "Principal should be greater than zero" in str(err.value)

def test_rate_validation():
    program = AccountingProgram()
    with pytest.raises(ValueError) as err:
        program.set_rate(-0.05)
    assert "Interest rate should be greater than zero" in str(err.value)

def test_years_validation():
    program = AccountingProgram()
    with pytest.raises(ValueError) as err:
        program.set_years(-10)
    assert "Years should be greater than zero" in str(err.value)

``` 

![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_037_test.jpg)
