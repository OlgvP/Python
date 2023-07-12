# Python challenges and exercises

###  Return the day

**Complete the function which returns the weekday according to the input number:**
```
def what_day():
    day = int(input('enter number 1-7\n'))
    days = { 				
			 1 : "Sunday",
			 2 : "Monday",
			 3 : "Tuesday",
			 4 : "Wednesday",
			 5 : "Thursday",
			 6 : "Friday",
			 7 : "Saturday" 
			 }
    print(days[day]) 
```
### If you can't sleep, just count sheep!!

**Given a non-negative integer, 3 for example, return a string saying: "1 sheep...2 sheep...3 sheep...".** 
**Input will always be valid, i.e. no negative integers.**	
```	
def count_sheep(number):
    for i in range(1, number + 1):
        output = ""
        output += str(i) + " sheep..."
        print(output, end="")

while True:
    number = int(input("\n Enter number >0 \n "))
    if number < 0:
        print('Enter correct number')
    else:
        count_sheep(number)	
```	
###  Is divisible ?

**Create a function `is_divisible()` that checks if a number `n` is divisible by two numbers `x` AND `y`. All inputs are positive, non-zero digits.

```
def is_divisible():
    while True:
        n = int(input('Enter number(0<)'))
        if n > 0:
            x = int(input('Enter number to check if the first number is divisible by this number(0<)'))
            if x > 0:
                y = int(input('Enter second number to check if the first number is divisible by this number(0<)'))
                if y > 0:
                    if (n % x == 0 and n % y ==0):
                        print("True because " + str(n) + " is divisible by " + str(x) + " and " + str(y))
                    elif (n % x != 0 and n % y !=0):
                        print("False because " + str(n) + " is neither divisible by " + str(x) + " and " + str(y))    
                    elif n % x != 0:
                        print("False because " + str(n) + " is not divisible by " + str(x))
                    elif n % y != 0:
                        print("False because " + str(n) + " is not divisible by " + str(y))
                   
is_divisible()
```

### Hello World

**Write a program that greets the user by name, or by saying "Hello,**
**World!" if no name is given.**

```
while True:
    x=input("Hello! What's your name?\n")
    if x:
        print("Hello, " + x + "!\n")      
    else:
        print("Hello, world!")
```

### Leap 

**Write a program that will take a year and report if it is a leap year.**
```
def leap_year(year):
    if year % 4 == 0 and (year % 100 != 0 or year % 400 == 0):
        print(str(year) + " is a leap year!")

while True:    
    year=int(input("Enter a year: \n"))
    leap_year(year)
```

### Pangram 
 **Determine if a sentence is a pangram**
 
``` 
import string 

def is_pangram(text):
    alphabet = set(string.ascii_lowercase)
    letters = set(text.lower())

    return alphabet.issubset(letters)
	
while True:
    text=input("Enter some text: \n")
    if is_pangram(text):
        print("It is pangram.\n")
    else:
        print("It is not pangram. \n")
```



 
### Word Count 

**Write a program that given a phrase can count the occurrences of each**
**word in that phrase.** 

```
from collections import Counter

def count_words(phrase):
    
    words = phrase.lower().split()
    word_counts = Counter(words)

    return word_counts
	
while True:
    phrase = input("Enter a phrase: \n")
    word_counts = count_words(phrase)

    for word, count in word_counts.items():
        print(f"{word}: {count}")
```


###  Bob 

**Bob is a lackadaisical teenager. In conversation, his responses are very**
**limited. Bob answers 'Sure.' if you ask him a question.**
**He answers 'Whoa, chill out!' if you yell at him.**
**He says 'Fine. Be that way!' if you address him without actually saying anything.**
**He answers 'Whatever.' to anything else.**

```
while True:
    bob = input("Hello, I'm Bob, what's up?")
    if "?" in bob:
        print("Sure.")
    elif "!" in bob:
        print("Whoa, chill out!")
    elif not bob:
        print("Fine. Be that way!")
    else:
        print("Whatever.")
```
		
## Allergies

**An allergy test produces a single numeric score which contains the information about all the allergies the person has (that they were tested for).**

**The list of items (and their value) that were tested are:**

**eggs (1)
**peanuts (2)
**shellfish (4)
**strawberries (8)
**tomatoes (16)
**chocolate (32)
**pollen (64)
**cats (128)
**So if Tom is allergic to peanuts and chocolate, he gets a score of 34.

**Now, given just that score of 34, your program should be able to say:**

**Whether Tom is allergic to any one of those allergens listed above.**
**All the allergens Tom is allergic to.**

```
allergylist = ["cats", "pollen", "chocolate", "tomatoes", "strawberries", "shellfish", "peanuts", "eggs"]
score=int(input("Enter the allergy number: \n"))
score = list((bin(score)[2:]).zfill(len(allergylist)))
for j, i in enumerate(score):
    if i == "1":
        print ("You are allergic to : " + allergylist[j])
```

## Grade School

**Write a small archiving program that stores student's names along with the grade that they are in.**

```
all_data = {}

def add_students(all_data):		#making directory with all data
    data = x.split() #spliting all phrase to list words
    name = data[1] # taking second word which is name
    grade = data[4] # taking fifth word which is number of grade
    all_data[name] = grade # adding to dictionary all_data name with number of grade           
    
def get_list_of_all(): # function for get a list of all students enrolled in a grade
    data = x.split()
    grade_nr = data[5]
    for key, value in all_data.items():
        if grade_nr == value:
            print ("We got: " + f"{key}")    

def get_sorted_list():

    output = ''
    grades = set(all_data.values())

    for grade in sorted(grades):
        students = [student for student, g in all_data.items() if g == grade]
        grade = int(grade)
        output += 'grade %d: %s, ' % (grade, ', '.join(students))
    output = output.rstrip(', ')
    print(output) 

   
x = input("how can I help you? (\"exit\" to quit)\n")
while not "exit" in x:
    if "Add" in x:
        add_students(all_data)
        print("Ok")
    elif "Which" in x:
        get_list_of_all()
    elif "Who" in x:
        get_sorted_list()
        break
    x = input("how can I help you? ('exit' to quit)\n")
```

## Prime factors

**Compute the prime factors of a given natural number.**

```
def print_factors(factors):
    string = ""
    for y in factors:
        string += (f"{y} * ")
    string = string[:-3]	#deleting ' * ' from the last factor
    print (string)

def prime_factor(x):
    factors = []
    div = 3
    while x > 1:
        if x%2 == 0:
            factors.append(2)
            x/=2
        elif x%div == 0:
            factors.append(div)
            x/=div
            div+=2
        else:
            div+=2
    print_factors(factors)


x = 1
x = int(input("Enter a number: "))
while x <= 1:
    x = int(input("Enter a number: "))
prime_factor(x) -->
```
