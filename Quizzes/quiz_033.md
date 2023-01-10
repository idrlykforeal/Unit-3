# code of mystery function:
```.py
def mystery(list1:list,list2:list)->list:
    output=[]
    for item1 in list1:
        for item2 in list2:
            if item1==item2:
                output.append(item1)
    return output
```
# code of automated testing:
```.py
import pytest
from quiz_033_u3 import mystery

def test_empty_lists():
  assert mystery([], []) == []

def test_one_common_element():
  assert mystery([1, 2, 3], [3, 4, 5]) == [3]

def test_multiple_common_elements():
  assert mystery([1, 2, 3, 4], [3, 4, 5, 6]) == [3, 4]
  ```
  
 # Automated test results
 <img width="686" alt="Screen Shot 2023-01-10 at 1 51 59 PM" src="https://user-images.githubusercontent.com/100017195/211464858-b30ec015-25e7-4e74-91c7-1142f2461cda.png">
