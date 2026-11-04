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
