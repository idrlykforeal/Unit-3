# Classes

```.py
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def get_name(self):
        if not isinstance(self.name, str):
            raise ValueError("Name must be a string")
        return self.name

    def get_age(self):
        if not isinstance(self.age, int):
            raise ValueError("Age must be an integer")
        return self.age

class Student(Person):
    def __init__(self,name,age,grade):
        super().__init__(name,age)
        self.name = name
        self.age = age
        self.grade = grade
    def get_grade(self):
        return self.grade

class Classroom():
    def __init__(self):
        self.students = []

    def add_student(self,student:Student):
        self.students.append(student)

    def remove_student(self,student:Student):
        if student not in self.students:
            raise ValueError("Invalid student: student not in classroom")
        self.students.remove(student)

    def get_average_score(self):
        if len(self.students) == 0:
            raise ValueError("Classroom is empty")
        total = 0
        for student in self.students:
            total += student.get_grade()
        average=total/len(self.students)
        return average
```

# test file
```.py
import pytest
from quiz_036 import Student, Classroom, Person

def test_student():
    student = Student("Jack", 17, 90)
    assert student.get_name() == "Jack"
    assert student.get_age() == 17
    assert student.get_grade() == 90
    with pytest.raises(ValueError):
        student = Student(["Jack"], 20 ,90)
        student.get_name()

def test_person():
    person = Person("Hello", 28)
    assert person.get_name() == "Hello"
    assert person.get_age() == 28
    with pytest.raises(ValueError):
        person2 = Person(123, "John")
        person2.get_name()
        person2.get_age()

def test_classroom():
    classroom = Classroom()
    student1 = Student("A", age=15, grade= 90)
    student2 = Student("B", age=16, grade= 87)
    student3 = Student("C", age=17, grade= 76)
    classroom.add_student(student1)
    classroom.add_student(student2)
    assert classroom.get_average_score() == (90+87)/2
    classroom.remove_student(student1)
    with pytest.raises(ValueError):
        classroom.remove_student(student3)
    with pytest.raises(ValueError):
        classroom.remove_student(student1)
        classroom.remove_student(student2)
        classroom.get_average_score()
```

# Test result
<img width="790" alt="Screen Shot 2023-01-26 at 9 58 10 PM" src="https://user-images.githubusercontent.com/100017195/214843755-9d5f7ace-becf-4a7d-9804-b6ad7e8f36c4.png">

