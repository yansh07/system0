## Here, we are going to explore how can we declare variables in shell scripting.  

**NOTE:** I am using ```zsh``` shell, yours may be different, check before running my scripts.  

## Variable declaration:  
```bash  
Name="Priyanshu"   #string  
Age=21  #integer  
echo "Hi, I am $Name and I am $Age years old"
 ```  
Output - "Hi, I am Priyanshu and I am 21 years old"  

**You can also change the value of variables, I think that's why we call them variable :)**  

### Now, let's see how we can store the value of an output in a variable: 

``` bash 
HOSTNAME=$(hostname)
echo "Name of the host is: $HOSTNAME"
```
Output - It will show your hostname  
**What actually happened?** -- So, ```hostname``` is a linux command which shows your machine name.  
We ran ```hostname``` and stored its value in a variable ```HOSTNAME``` and then we printed it using ``` echo ```.  

### Now, suppose you declared a variable and you want to keep it constant, and noone can change it - here we use ``` readonly ```  
```bash 
#!/bin/zsh
echo "Hello!!"
readonly name="Priyanshu"
age=21

echo "Hi, I am $name"

name = "Anshu"
```
As soon as we used ```readonly```, now we cannot change the value of **name** variable and if tried to run - we will get an error.  

## Now, let's see how can we take input from user:  
```bash
#!/bin/zsh

echo "What's your name bro?"
read user_name #pauses and waits for input

echo "Welcome, $user_name. We've been expecting you"
```
Output: 
What's your name bro?  
anshu  
Welcome, anshu. We've been expecting you  

### Another way to do this is:  
```bash
#!/bin/zsh
print -n "Enter your name honey: "
read codename
print "Welcome again, $codename"
```  

### Let's make a small calculator script:  
```bash
#!/bin/zsh
print -n "Enter num1: " #use -n to avoid new line for input
read num1
print -n "Enter num2: "
read num2
#sum="$num1 + $num2" # this will output (12+12)
#print "$sum"
sum2="$((num1+num2))" # this will output 24
print "$sum2"
```

**Magic:** Without the ```$((...))``` part, if you tried let ```sum="$num1 + $num2"```, you'd get an error because the shell would be trying to add strings.

## Now, the bracket magic:  
1. Double Quotes ```"```: Allows variable expansion. The shell looks inside for variables (like $name) and replaces them with their value.  

2. Single Quotes ```'```: Literal string. The shell treats every single character inside literally. No variable expansion.  

```bash
#!/bin/zsh

user="Priyanshu"

# Double quotes will replace $user with its value
echo "Hello, $user" 

# Single quotes will print the literal text '$user'
echo 'Hello, $user'
```  
Output:   
Hello, Priyanshu  
Hello, $user  

## Let's do some fun with string:  
```bash
#!/bin/zsh

secret="AGENT_PRIYANSHU"
echo "Original: $secret" #will print original string
echo "Code: ${#secret}" #will print string length
```  
```bash
#!/bin/zsh

secret="AGENT_PRIYANSHU"
agent=${secret:6:9} #string slicing
print "Identified agent: $agent" #output - PRIYANSHU
```  
### If else statement:  
```bash
#!/bin/zsh

print -n "Enter your age: "
read user_age
if ((user_age >= 18)); then
        print "You can drive"
else
        print "You are a minor, and cannot drive"
fi
``` 
Output:  
```Enter your age: 12  ```  
```You are a minor, and cannot drive```  
&  
``` Enter your age: 21```  
```You can drive ```  
