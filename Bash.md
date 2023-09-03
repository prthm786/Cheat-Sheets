#            Bash 

> [Variables](#Variables)

> [Operators](#Operators)

> [Conditionals (If-Else and Case)](#Conditionals)

> [Loops (For, While and Until loop)](#Loops)

> [Arrays](#Arrays)
 
> [Functions](#Functions)

> [Strings](#Strings)
---


### Variables
--- 

```bash
<Var_Name>=<Value>
MYVAR="Hello World"

echo "$MYVAR" # printing a variable  
echo "${MYVAR}"
``` 

Reading Input from the user 
```bash 
read -p "Enter Input" input 
echo "$input"
``` 

Creating Random Numbers 
```bash
# Creating a random integer between 0 and 32,767
randNo=$RANDOM

# Print the random number
echo "Random Number: $randNo"

randNo=$((RANDOM % 10))
# Random No between 0 to 9
echo "Random No between 0 to 9: $randNo"

```
---
---


### Operators
---

Conditional Operators

> -eq: Equal to

> -ne: Not equal to

> -lt: Less than

> -le: Less than or equal to

> -gt: Greater than

> -ge : Greater than or equal to

> ==: String equality

> !=: String inequality


Arithmetic Operators 

> +: Addition

> -: Subtraction 

> *: Multiplication 

> /: Division 

> %: Modulus  

> **: Exponentiation 

> ++: Increment Operator 

> --: Decrement Operator 


Logical Operators
> &&: Logical AND 

> ||: Logical OR

> !: Not Equal to


Bitwise Operators
> &: Bitwise And 

> |: Bitwise OR 

> Bitwise XOR (^) 
 
> ~: Bitwise complement


File Test Operator
> -b operator # block special file

> -c operator # character special file

> -d operator # directory

> -e operator # exists

> -r operator # read access

> -w operator # write access

> -x operator # execute access 

> -s operator

> -f operator

---
---


### Conditionals
---

If-Else 

```bash
if [[ condition ]]
then
    # Commands to execute if the condition is true
fi 
```

```bash
if [[ condition ]]
then
    # Commands to execute if the condition is true
else
    # Commands to execute if the condition is false
fi
```


Case Statement

```bash
case $Var in
    0)
        Echo “Zero!”
        ;;
    1)
        Echo “One!”
        ;;

    *)
        Echo “Invalid”
        ;;
esac

```
---
---


### Loops 
---

For Loop

```bash
for $Var in <Array>
do
    # loop 
done 
``` 

Traditional For loop
```bash 
numbers=()
for ((i=97; i<=122; i++)) 
do
   numbers+=( "$i" )
done
```

Iterating Through An Array
```bash
numbers=”One Two Three List”
for n in $numbers
do
    echo $n
done
```

Iterating Through a Range
```bash
for number in {1..5}
do
    echo "Number: $number"
done
```

Iterating Through Files
```bash
for file in /path/to/directory/*
do
    if [ -f "$file" ]; then
        echo "$(cat $file)" 
        # printing the contents of a file using Command Substitution
    fi
done
```

While loop

```bash
while [ <condition> ]
do
    # loop 
done
```

Example
```bash
C=0
while [ $C -le 5 ]
do
    echo -n “$C“
    ((C++))  # incrementing count var
done

```
---
---


### Arrays
---

Array Creation 
```bash
ARRAY=("ABC" "BCD" "CDE" "EFG")
echo $ARRAY
```

Printing Array Length
```bash
echo " Length of Array: ${#ARRAY(@)}"
```

Looping through an Array
```bash
for Element in "${ARRAY[@]}" 
do
    echo "$Element"
done
```

Concatenating Arrays
```bash
arr1=("apple" "banana" "cherry")
arr2=("orange" "pear" "guava")

mergedArr=("${arr1[@]}" "${arr2[@]}")

# Looping through the merged array
for item in "${mergedArr[@]}"
do
    echo "Merged Array: $item"
done
```

Using Brace expansion to create the array
```bash
letters=({a..z})

# Print the array
echo "${letters[@]}"

```
---
---


### Functions 
---

Function without an Argument 
```bash
# Function Creation 
hello_world() {
    echo "Hello World" 
}
# Calling a function  
hello_world 
```

Function with an Argument 
```bash
func_with_arg() {
  echo "Arg1: $1"
  echo "Arg2: $2"
  echo "All Argument: $@"
}

func_with_arg 12 23 

```
---
---


### Strings
---

```bash
STR_VAR="Hello World" 

# Length of string variable 
LEN=${#STR_VAR}
echo $LEN

# Substring Extraction 
SUBSTR="${STR_VAR:0:5}" 
echo $SUBSTR
# Output "Hello"

# String Concatenation 
STR1="Hello"
STR2="World"
CONCAT_STR="$STR1 $STR2" 
echo $CONCAT_STR
# Output "Hello World"

# Substring Replacement
NEW_STR="${STR_VAR/World/Universe}" 
echo $NEW_STR
# "World" with "Universe"

```
---
---