# Quiz 034

## Code
```.py
class to_roman:

    def __init__(self, num:int):
        self.num = num
    def solve(self):
        numbers = [100, 90, 50, 40, 10, 9, 5, 4, 1]
        roman_numerals = ["C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"]
        finalnum = ""
        if self.num<1 or self.num>100:
            raise ValueError("Number must be between 1 and 100")
        if not isinstance(self.num, int):
            raise TypeError("Inputs must be integers")
        while self.num > 0:
            for i in range(len(numbers)):
                if self.num >= numbers[i]:
                    self.num -= numbers[i]
                    finalnum += roman_numerals[i]
                    break
        return finalnum
```
## Test Case 
```.py 
from quiz_034 import to_roman
import pytest

def test_to_roman():
    assert to_roman(1).solve() == 'I'
    assert to_roman(4).solve() == 'IV'
    assert to_roman(9).solve() == 'IX'
    assert to_roman(37).solve() == 'XXXVII'
    assert to_roman(44).solve() == 'XLIV'
    assert to_roman(50).solve() == 'L'
    assert to_roman(99).solve() == 'XCIX'
    assert to_roman(100).solve() == 'C'
    assert to_roman(77).solve() == 'LXXVII'
    assert to_roman(93).solve() == 'XCIII'


def test_to_roman_exceptions():
    # check that the program raises a ValueError
    with pytest.raises(ValueError):
        to_roman(101).solve()

``` 

![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_034_test.jpg)
