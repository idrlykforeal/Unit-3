# code of class
```.py
class quiz34:
    def __init__(self, num:int):
        self.num = num
    def solve(self):
        out=""
        roman= {100:'C', 90:'XC', 50:'L', 40:'XL', 10:'X', 9:'IX', 5:'V', 4:'IV', 1:'I'}
        if self.num < 1 or self.num >100:
            raise ValueError("Number must be between 1 and 100")
        if not isinstance(self.num,int):
            raise TypeError("Number must be an integer")
        while self.num>0:
            for i in roman.keys():
                if self.num>=i:
                    out+=roman[i]
                    self.num-=i
                    break
        return out
```
# test code
```.py
import pytest
from quiz_034 import quiz34

def test_5():
    assert quiz34(5).solve() == 'V'

def test_not_int():
    with pytest.raises(TypeError):
        assert quiz34("a").solve()
def test_out_of_range():
    with pytest.raises(ValueError):
        assert quiz34(101).solve()
def test_37():
    assert quiz34(37).solve() == 'XXXVII'
```

# test results
<img width="686" alt="Screen Shot 2023-01-12 at 9 55 10 AM" src="https://user-images.githubusercontent.com/100017195/211950185-01432d4a-5364-4951-9721-cb46338bc248.png">
