# Python challenges


### Hello World

**Write a program that greets the user by name, or by saying "Hello,**
**World!" if no name is given.**

while True:
    x=input("Hello! What's your name?\n")
    if x:
        print("Hello, " + x + "!\n")      
    else:
        print("Hello, world!")

### Leap 

**Write a program that will take a year and report if it is a leap year.**

def leap_year(year):
    if year % 4 == 0 and (year % 100 != 0 or year % 400 == 0):
        print(str(year) + " is a leap year!")

while True:    
    year=int(input("Enter a year: \n"))
    leap_year(year)

### Pangram 
 **Determine if a sentence is a pangram**
 
 
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



 
### Word Count 

**Write a program that given a phrase can count the occurrences of each**
**word in that phrase.** 

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


###  Bob 

**Bob is a lackadaisical teenager. In conversation, his responses are very
limited. Bob answers 'Sure.' if you ask him a question.
He answers 'Whoa, chill out!' if you yell at him.
He says 'Fine. Be that way!' if you address him without actually saying anything.
He answers 'Whatever.' to anything else.**

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
