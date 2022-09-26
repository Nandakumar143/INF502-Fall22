## Question 1

Write a function with the following signature: pythagoreanTheorem(length_a, length_b).

The function returns the length of the hypotenuse assuming that length_a and length_b are the lengths of the two legs of a right triangle (the legs that form the triangle's right angle). Hint: the math module might have useful functions to use.

For example:

> print(pythagoreanTheorem(2, 2))   result: 2.8284271247461903

[code](code)
```python3
import math

def pythagoreanTheorem(length_a, length_b):
    return math.sqrt(length_a ** 2 + length_b ** 2)  # return the square root of square(length_a + length_b)

print(pythagoreanTheorem(3,4))
print(pythagoreanTheorem(5,4))
print(pythagoreanTheorem(6,9))
```


## Question 2

Write a function with the following signature: list_mangler(list_in).

The function assumes that list_in is a list of integers, and returns a new list containing transformed elements of list_in. If the element is even, it's doubled. If the element is odd, it's tripled.

> print(list_mangler([1, 2, 3, 4]))    result:[3, 4, 9, 8]

```python3
def list_mangler(list_in):
    for ele in list_in:  # go through the list
        if ele % 2 != 0:  # if it is odd
            ele *= 3  # multiply by 3
        else:  # else if even
            ele *= 2  # multiply by 2
    return list_in  # return the final list
    
print(list_mangler([90, 35, 23, 6]))
print(list_mangler([7, 9, 8, 35]))
print(list_mangler([8, 90, 9, 65, 36]))

```

## Question 3

Write a function with the following signature: grade_calc(grades_in, to_drop).

The function accepts a list grades_in containing integer grades, drops the to_drop lowest grades (so, for to_drop equal to 2, the function should drop the 2 lowest grades), calculates the average of the grades left, and returns the letter grade this average corresponds to according to the letter grade scale for this course.

> print(grade_calc([100, 90, 80, 95], 2)) # drops the 2 lowest grades (80 and 90)  result: "A"

```python3
def grade_calc(grades_in, to_drop):
    grades_in.sort()  # sort the list of grades
    grades_in[to_drop:]  # remove the first few elements till to_drop
    
    average = sum(grades_in)/len(grades_in)  # gets the average by summation and divides by length
    
    if average > 90:  # case if average is greater then 90
        return "A"
    elif 80 <= average < 90:  # case if average is greater then 70 and less than 80
        return "B"
    elif 70 <= average < 80:  # case if average is greater then 70 and less than 80
        return "C"
    elif 60 <= average < 70:  # case if average is greater then 60 and less than 70
        return "D"
    else:  # case if average is less than 60
        return "F"
  
print(grade_calc([90, 86, 95, 100, 65], 3))
print(grade_calc([90, 86, 100, 100], 2))
print(grade_calc([40, 40, 60, 35, 100], 2))
```

## Question 4

Write a function with the following signature: odd_even_filter(numbers).

The function accepts an input list of integers and returns a list with two sublists. The first sublist contains all even numbers in the input list and the second sublist contains all odd numbers.

> print(odd_even_filter([1, 2, 3, 4, 5, 6, 7, 8, 9]))    result: [[2, 4, 6, 8], [1, 3, 5, 7, 9]]
```python3
def odd_even_filter(numbers):
    odd_list = []  # empty list to store odd numbers
    even_list = []  # empty list to store even numbers
    
    for ele in numbers:  # go through numbers
        if ele % 2 != 0:  # if odd
            odd_list.append(ele)  # add to odd list
        else:
            even_list.append(ele)  # add to even list
            
    return [odd_list, even_list]  # return list of even and odd integers

print(odd_even_filter([30, 3, 25, 20, 15, 12]))
print(odd_even_filter([3, 13, 257, 2, 1, 6]))
print(odd_even_filter([4, 6, 8]))
```
