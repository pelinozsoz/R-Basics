# Operators
Operators are the symbols that tell R what kind of opration will be performed to operands.
## 🧮 Arithmetic Operators
Arithmetic Operators are used for basic mathematical calculations.
```r
# +	--> Addition
3 + 2

# -	--> Subtraction
10 - 4

# *	--> Multiplication
5 * 3 

# /	--> Division
10 / 2

# ^ or **	--> Exponentiation (power)
2 ^ 3

# %%	--> Modulus (remainder after division)
10 %% 3

# %/%	--> Integer division (quotient without remainder)
10 %/% 3
```
## 💡 Relational (Comparison) Operators
Relational operators are Used to compare two values — the result is TRUE or FALSE.
```r
# == --> Equal to
5 == 5

# != --> Not equal to
5 != 3

# > --> Greater than
7 > 2

# < --> Less than
3 < 10

# >= --> Greater than or equal to
6 >= 6

# <= --> Less than or equal to
2 <= 3
```
## 🔎 Logical Operators
Logical operators are used to combine logical (TRUE/FALSE) statements.
```r
# & --> AND (checks all elements)
c(TRUE, FALSE, TRUE) & c(TRUE, TRUE, FALSE)

# && --> AND (checks only first element)
TRUE && FALSE

# | --> OR (checks all elements)
c(TRUE, FALSE, FALSE) | c(FALSE, FALSE, TRUE)

# || --> OR (checks only first element)
TRUE || FALSE

# ! --> NOT (reverses logical value)
!TRUE
```
## 🗝️ Assignment Operators
Assignment operators are used to assign values to variables.
```r
# <- --> Assigns value to a variable (most common)
x <- 10

# -> --> Assigns value from left to right
10 -> y

# = --> Another way to assign value
z = 20
```
# 🗂️ Miscellaneous Operators
Miscellaneous Operators other useful operators used in R.
```r
# : --> Sequence operator
1:5

# %in% --> Checks if an element is in a vector
3 %in% c(1,2,3,4)

# %*% --> Matrix multiplication
matrix(c(1,2), nrow=1) %*% matrix(c(3,4), ncol=1) → 11

# $ --> Access elements by name in a list or data frame
data$age

# [] --> Access elements by position or name
x[2]

# [[]] --> Extract single element from a list
mylist[[1]]

# @ --> Access slots in S4 objects (advanced OOP feature)
obj@slotname
```

