#            Bash 

> Variables 

> Operators

> Conditionals (If-Else and Case)

> Loops (For, While and Until loop)

> Array Handling
 
> Functions 
 


### Variables
--- 

```bash
<Var_Name>=<Value>
MYVAR="Hello World"

echo "$MYVAR" # printing a variable  
echo "${MYVAR}"
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
> -b operator  # block special file

> -c operator  # character special file

> -d operator  # directory

> -e operator  # exists

> -r operator  # read access

> -w operator  # write access

> -x operator  # execute access 

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
Numbers=”One Two Three List”
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

Eg:- 
```bash
C=0
while [ $C -le 5 ]
do
    Echo -n “$C“
    ((c++)) 
 done
```
---
---


### Array Handling
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

# Using Brace expansion to create the array
```bash
letters=({a..z})

# Print the array
echo "${letters[@]}"
```
---
---


### Functions 
---
Function Creation 
```bash
hello_world() {
    echo "Hello World" 
}
``` 
Function calling 
```bash 
hello_world 
```

Function with an Argument 
```bash
func_with_arg() {
  echo "Arg1: $1"
  echo "Arg2: $2"
}

func_with_arg 12 23 
```
---
---


