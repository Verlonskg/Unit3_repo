# Quiz 036

## Code
```.py
class Person:

    def __init__(self, name:str, age:int):
        self.name = name
        self.age = age

    def get_name(self)->str:
        return self.name

    def get_age(self)->int:
        return self.age

class Student(Person):

    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade
        self.name = name
        self.age = age

    def get_grade(self):
        return self.grade


class Classroom:
    def __init__(self):
        self.students = []

    def add_student(self, student: Student):
        self.students.append(student)

    def remove_student(self, student: Student):
        if student not in self.students:
            raise ValueError("Student not in classroom")
        self.students.remove(student)

    def get_average_score(self):
        if len(self.students) == 0:
            raise ValueError("Classroom is empty")
        total = 0
        for student in self.students:
            total += student.get_grade()
        return total / len(self.students)

```
## Test Case 
```.py 
import pytest
from quiz_036 import Student
from quiz_036 import Classroom

def test_add_student():
    classroom = Classroom()
    student = Student("John", 18, 90)
    classroom.add_student(student)
    assert student in classroom.students

def test_remove_student():
    classroom = Classroom()
    student = Student("John", 18, 90)
    classroom.add_student(student)
    classroom.remove_student(student)
    assert student not in classroom.students

def test_remove_non_existing_student():
    classroom = Classroom()
    student = Student("John", 18, 90)
    with pytest.raises(ValueError):
        classroom.remove_student(student)

def test_get_average_score():
    classroom = Classroom()
    student1 = Student("John", 18, 90)
    student2 = Student("Jane", 19, 80)
    classroom.add_student(student1)
    classroom.add_student(student2)
    assert classroom.get_average_score() == (90 + 80) / 2

def test_empty_classroom():
    classroom = Classroom()
    with pytest.raises(ValueError):
        classroom.get_average_score()

``` 

![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_036_test.jpg)
