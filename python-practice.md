## Date: 2/11/26
**Python**  

##Exercise-1  
print(f"The house was a good size: 1200 square feet, or {1200 * 0.092903:.0f} meters squared!")

##Exercise-2  
l=30  
w=58  
area=l*w  
print(f"""The area of my  house {l*w} feet squared!  
which is {area*0.0929} meter squared  
""")

##Exercise-3   
name="abrez"  
age=50   
print_llm_response(f"""i am {name} who is {age} year old.  
give me the ideal diet plan  

""")
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
