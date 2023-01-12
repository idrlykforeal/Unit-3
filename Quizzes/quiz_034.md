# code of function
```.py
def to_roman(num:int):
    out=""
    roman= {100:'C', 90:'XC', 50:'L', 40:'XL', 10:'X', 9:'IX', 5:'V', 4:'IV', 1:'I'}
    if num < 1 or num >100:
        raise ValueError("Number must be between 1 and 100")
    if not isinstance(num,int):
        raise TypeError("Number must be an integer")
    while num>0:
        for i in roman.keys():
            if num>=i:
                out+=roman[i]
                num-=i
                break
    return out
```
# test code
```.py
import pytest
from quiz_034 import to_roman

def test_5():
    assert to_roman(5) == 'V'
def test_not_int():
    with pytest.raises(TypeError):
        to_roman("a")
def test_out_of_range():
    with pytest.raises(ValueError):
        to_roman(101)
def test_37():
    assert to_roman(37) == 'XXXVII'
```

# test results
<img width="686" alt="Screen Shot 2023-01-12 at 9 55 10 AM" src="https://user-images.githubusercontent.com/100017195/211950185-01432d4a-5364-4951-9721-cb46338bc248.png">
