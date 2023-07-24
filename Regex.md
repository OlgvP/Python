### Regex

1. Create a regex that finds integers without size limit.

s = "sssgdds8sfsfs"

```
import re

s = "sssgdds8sfsfs"
print(re.findall("([0-9]+)", s))
```

2. Create a regex that finds negative integers without size limit.

s = "sssgdds-8sfsfs"

```
import re
s = "sssgdds-8sfsfs"
print(re.findall("(-?[0-9]+)", s))
```

3. Create a regex that finds (positive or negative) integers without size limit.

```
import re
s = "sssgdds-8s8fsfs"

print(re.findall("(-?[0-9]+?)", s))
```

4. Capture all the numbers of the following sentence :


text = "21 scouts and 3 tanks fought against 4,003 protestors, so the manager was not 100.00% happy."

```
import re

text = "21 scouts and 3 tanks fought against 4,003 protestors, so the manager was not 100.00% happy."

numbers = re.findall(r'\d+(?:,\d+)*(?:\.\d+)?', text)
print(numbers)
``` 


5. Find all words that end with 'ly'.

text = "He had prudently disguised himself but was quickly captured by the police."

```
import re

text = "He had prudently disguised himself but was quickly captured by the police."
x = ("\w*ly")
result = re.findall(x, text)
print(result)
```

6. License plate number.

A license plate consists of 2 capital letters, a dash ('-'), 3 digits, a dash ('-') and finally 2 capital letters.
Write a script to check that an input string is a license plate.
If it's correct, print "good". If it's not correct, print "Not good".

```
import re

while True:
    plate = input("Enter your license plate number: ")
    x = ("[A-Z]{2}[-][0-9]{3}[-][A-Z]{2}")
    if re.match(x, plate):
        print("good")
    else:
        print("not good")
```


7 . Address IPV4.

An IPv4 address is composed of 4 numbers between 0 and 255 separated by '.'
Write a script to verify that a string entered is that of an IPv4 address.

```
import re


ip = input("Enter your IP address : ")

x = r"^(([01]?[0-9]?[0-9]|2[0-4][0-9]|25[0-5])\.){3}([01]?[0-9]?[0-9]|2[0-4][0-9]|25[0-5])$"


if re.match(x, ip):
    print("It is an IP address")            
else:
    print("It is NOT an IP address")
```	
	
8. Valid Mail

An email is composed of alphanumeric characters followed by @ and a domain name.
Write a script that checks that the string entered by a user is indeed that of an email,
otherwise ask him to re-enter it again (until he gets a valid email).

```
import re

x = ("([A-Za-z0-9]+[.-_])*[A-Za-z0-9]+@[A-Za-z0-9-]+(\.[A-Z|a-z]{2,})+")
mail = input("Enter your email(type exit to quit): ")

while True:
    
    if not re.match(x, mail):
        print("It's not a valid mail")
        mail = input("Enter your email: ")
    else:
        print("It is a valid mail")
        break
```

9. Valid Password

Write an additional script that verifies the password (obviously if the email is valid) 
where the only specificity of the password is that it has to contain at least 6 characters.

```
def valid_password():
    y = r'^.{6}$'
    password = input("Enter your password: ")
    while not re.match(y, password):
        print("wrong password")
        password = input("Enter your password: ")
        if re.match(y, password):
            print("Good")
            return

        
import re

x = ("([A-Za-z0-9]+[.-_])*[A-Za-z0-9]+@[A-Za-z0-9-]+(\.[A-Z|a-z]{2,})+")
mail = input("Enter your email: ")

while True:    
    if not re.match(x, mail):
        print("It's not a valid mail")
        mail = input("Enter your email: ")
    else:
        print("It is a valid mail")
        valid_password()
        break
```

10. Valid Password bis

The password must now contain at least 6 characters AND

at least one lowercase letter AND
at least one uppercase letter AND
at least one number AND
at least one special character (among $#@).

In this exercise we can use the same code as in last exercise but we
need to just change the variable with regex (which we are comparing with password).
In this case is variable y from function valid_password. 
New variable:

```
y = r'^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[$#@]).{6,}$'
```







