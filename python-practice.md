## Date: 2/11/26
**Python**  

## Exercise-1  

```python

print(f"The house was a good size: 1200 square feet, or {1200 * 0.092903:.0f} meters squared!")
```
## Exercise-2

```python
l=30  
w=58  
area=l*w  
print(f"""The area of my  house {l*w} feet squared!  
which is {area*0.0929} meter squared  
""")
```
## Exercise-3

```python
name="abrez"  
age=50   
print_llm_response(f"""i am {name} who is {age} year old.  
give me the ideal diet plan  

""")
````
## Task 2: frame-to-timecode converter (24 fps)

## What you’re building: you enter a number of frames, and the program tells you how many seconds and leftover frames that is.

Part 1, two helpers:

seconds(frames) gives back the number of whole seconds.
leftover(frames) gives back the frames left over.
Neither one prints.

Which operator does each helper need? Look back at the 100-frame example.

Part 2, main:

It asks for the total frames.
It gets the answers back from both helpers.
It prints the result in this form: 4 seconds 4 frames

```python
def main():
    frames = int(input("Enter total frames: "))

    sec = seconds(frames)
    rem = leftover(frames)
    print(sec,"seconds",rem,"frames")

def seconds(frames):
    return frames // 24


def leftover(frames):
    return frames % 24


main()
```

PS D:\AI\github\Python> python 511.py
Enter total frames: 100
4 seconds 4 frames
PS D:\AI\github\Python> python 511.py
Enter total frames: 48
2 seconds 0 frames
PS D:\AI\github\Python> python 511.py
Enter total frames: 23
0 seconds 23 frames

## Task 3: sharing chocolates

## What you’re building: you enter a number of chocolates and a number of children. The program says how many each child gets and how many are left over.

Part 1, two helpers:

each_gets(chocolates, children) gives back how many whole chocolates each child gets.
left_over(chocolates, children) gives back how many are left over.
Neither one prints.

Part 2, main:

It asks for the chocolates, then the children.
If the number of children is 0, it prints no children to share with and doesn’t call the helpers. Think about why: what happens when you divide by 0?
Otherwise it prints two lines, as shown below.


```python
def main():
    choclates = int(input("Enter chocolates: "))
    children = int(input("Enter children: "))


    if children == 0:
        print("no children to share with")
    else:
        share = each_gets(choclates, children)
        remaining = left_over(choclates, children)

         
        print("Each child gets:", share)
        print("Left over:", remaining)


def each_gets(choclates, children):
    return choclates // children


def left_over (choclates, children):
    return choclates % children
  

main()

```

PS D:\AI\github\Python> python 511.py
Enter chocolates: 17
Enter children: 5
Each child gets: 3
Left over: 2
PS D:\AI\github\Python> python 511.py
Enter chocolates: 10
Enter children: 5
Each child gets: 2
Left over: 0
PS D:\AI\github\Python> python 511.py
Enter chocolates: 7
Enter children: 0
no children to share with
PS D:\AI\github\Python>

## What you’re building: a day checker that uses match.

Part 1, a helper called day_type(day):

"Saturday" or "Sunday" gives back weekend.
"Monday" to "Friday" gives back weekday.
Anything else gives back invalid.
It uses match, not if, and has no print.

Part 2, main: asks for the day, gets the answer back, and prints it.


```python
def main():
    day = input("Enter the day: ")
    result = day_type(day)
    print(result)


def day_type(day):
    match day:
        case "Monday" | "Tuesday" | "Wednesday" | "Thursday" | "Friday":
            return "weekday"
        case "Saturday" | "Sunday":
            return "weekend"
        case _:
            return "invalid"


main()
```

PS D:\AI\github\Python> python conditional.py
Enter the day: Sunday
weekend
PS D:\AI\github\Python> python conditional.py
Enter the day: Wednesday
weekday
PS D:\AI\github\Python> python conditional.py
Enter the day: Funday
invalid


## Part 1, a helper called get_marks():

It keeps asking Enter marks: until the number is from 0 to 100.
It gives back the good number with return.
It has no print.

## Part 2, main():

It asks how many subjects there are.
It loops that many times, calling get_marks() each time and adding the result to the total.
After the loop, it prints the total and the average.


```python
def main():

    subjects = int(input("How many subjects: "))
    total = 0

    for _ in range(1, subjects+1):

        marks = get_marks()
        total = total + marks

    average = total / subjects

    print("Total:", total)
    print("Average:", average)


def get_marks():

    while True:

        marks = int(input("Enter marks: "))

        if 0 <= marks <= 100:
            return marks


main()
```

How many subjects: 2
Enter marks: 150
Enter marks: 80
Enter marks: -5
Enter marks: 90
Total: 170
Average: 85.0

## This combines lists, a running total and a counter. It’s close to your gate’s “loop and list” item.

New shortcut (optional): total += m means exactly the same as total = total + m.

Inside main():

Start an empty list called marks.
Ask how many subjects there are, then loop that many times, appending each mark (as a whole number) to the list.
Then loop over the list with for m in marks:, and inside that loop:
add each mark to a total
if the mark is 50 or more, add 1 to a passed counter
After the loop, print 4 lines using f-strings.
```python

def main():
    subjects = int(input("How many subjects: "))
    marks = []
    total = 0
    passed = 0

    for _ in range(1, subjects + 1):
        number = int(input("Enter marks: "))
        marks.append(number)

    for num in marks:
        total = total + num
        if num >= 50:
            passed = passed + 1

    print(f"Marks: {marks}")
    print(f"Total: {total}")
    print(f"Average: {total / len(marks):.2f}")
    print(f"Passed: {passed} of {len(marks)}")


main()
```

## Exercise  — Understanding how to create a new dictionary
The objective is to create a second dictionary containing only students who passed, without changing the original dictionary.

```python
students = {
    "Amit": [85, 90, 78],
    "Rahul": [32, 45, 38],
    "Priya": [95, 92, 98],
    "Neha": [68, 75, 70],
    "Karan": [25, 35, 30]
}

passed_students = {}
passed = 0
failed = 0


for student, marks in students.items():
    total = sum(marks)
    average = total / len(marks)

    if average >= 40 :
  
        result = "Passed"
        passed = passed + 1
        passed_students[student] = average 

    else:

        result = "Failed"
        failed = failed + 1


    print(f"{student} - Total : {total}, Average: {average:.2f}, - {result}")

print ("Total Passed:", passed)
print ("Total Failed:", failed)
print ()

print(passed_students)
```
