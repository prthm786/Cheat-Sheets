#            Bash 

### Variables 

### Operators

### Conditionals (If-Else and Case)

### Loops (For, While and Until loop)

### Array Handling
 
### Functions 
 


### Variables

<Var_Name>=<Value>
MYVAR="Hello World"

echo "$MYVAR" # printing a variable  
echo "${MYVAR}"


### Operators

Conditional Operators

-eq: Equal to
-ne: Not equal to
-lt: Less than
-le: Less than or equal to
-gt: Greater than
-ge: Greater than or equal to
==: String equality
!=: String inequality


Arithmetic Operators 

+: Addition
-: Subtraction 
*: Multiplication 
/: Division 
%: Modulus  
**: Exponentiation 
++: Increment Operator 
--: Decrement Operator 


Logical Operators
&&: Logical AND 
||: Logical OR
!: Not Equal to


Bitwise Operators
&: Bitwise And 
|: Bitwise OR 
Bitwise XOR (^)  
~: Bitwise complement


File Test Operator
-b operator  # block special file 
-c operator  # character special file
-d operator  # directory
-e operator  # exists
-r operator  # read access
-w operator  # write access
-x operator  # execute access 
-s operator
-f operator


### Conditionals

If-Else 

`
if [[ condition ]]
then
    # Commands to execute if the condition is true
fi 
`


`
if [[ condition ]]
then
    # Commands to execute if the condition is true
else
    # Commands to execute if the condition is false
fi
`  

Case Statement
`
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
`


### Loops 

For Loop

for $Var in <Array>
do
    # loop 
done 

Eg:-
`
Numbers=”One Two Three List”
for n in $numbers
do
    echo $n
done
`

While loop

`
C=0
while [ $C -le 5 ]
do
    Echo -n “$C“
    ((c++)) 
 one
`
