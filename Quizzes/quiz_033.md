# Quiz 033

## Code: 

```.py
def mystery(x:list, y:list)->list:
    
    output = []
    
    for i in range(len(x)):
        xnum = x[i]
        for i in range(len(y)):
            ynum = y[i]
            if xnum == ynum:
                output.append(xnum)
                
    return output
```
## Test Case: 
```.py 
import pytest
from quiz_033 import mystery


def test_empty_lists():
    assert mystery([], []) == []


def test_one_common_element():
    assert mystery([1, 2, 3], [3, 4, 5]) == [3]


def test_multiple_common_elements():
    assert mystery([1, 2, 3, 4], [3, 4, 5, 6]) == [3, 4]
``` 

![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_033_test.jpg)
