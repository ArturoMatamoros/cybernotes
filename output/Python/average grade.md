# #Lab —  average grade on python

**Goal:** to practice with simple things like if, cycles and lists
**Attempt:** the project was fairily easy with some little notes to take on sintax
**Broke:** The input function was something I did not remember
**Fixed:** The solution was pretty simple and it worked out
**Learned:** basic sintax, list methods like append

```python 

grades = []

#starting the cicle to register the grades 
while True :
    vote=input("insert the vote: ")
    if vote == "done" : 
        break
    grades.append(int(vote))

#calculating the average
total=0
for g in grades: 
    total+=g

average = total / len(grades)
print("your average vote is: " + str(average))

#calculating if he passed

if average < 6 : 
    print("you did not pass this year")
else : 
    print("you passed")

#finding the lowest and highest score

grades.sort()

print("your highest score is: " + str(grades[-1]))
print("your lowest score is: " + str(grades[0]))


```
**links:** 
- [[Python]]
	- [[liste e array in Python]]
	- [[Automate the boring stuff with python]] 