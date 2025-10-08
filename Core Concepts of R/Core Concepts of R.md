# Core Concepts in R

## 📘Basic Syntax
In programming, syntax defines the set of rules that describes how the code must be written so that computer can understand it.

- Strings must be introduced with quotation mark.
  
```r
"Hello World!" 
print("Hello World!")
```
- Numbers must be introduced without quotation mark.
```r
10
print(10)
```
- Any type of data can be stored as variables via "<-"
```r
x <- "my text"
y <- 22
```
- Comments can be introduced with #.
```r
#This is a comment.
```
- Reserved words also a part of R syntax and each of them have a special meaning for R language therefore, they can not be used as variable names of identifiers.
```r
if, else, for, while, TRUE, FALSE...
```
## 📗Variables
Variables are memory units of R where any type of data can be stored and manipulated. A value can be assign to a variable via "<-" sign.
```r
color <- "pink"
number <- 30

color
number

print(color)
print(number)
```
### 📎How to name variables?
- Variables can be named with letters (A-Z, a-z), numbers (0-9), underscores (_), and dots (.).
- Letters and dot can be used as the beginning character, however, a variable can not begin with numbers or underscores.
- Reserved words can not be used as variable names.
```r
# Valid variable names:
fruit <- "banana"
my_age <- 22
variable_1 <- "candy"
.number <- 34

# Invalid variable names
book& <- " The Little Prince"
.25 <- 25
for <- "flower"
_class <- "senior"
```
## 📙Data Types
Data type refers to the kind of data that is stored in a variable. Data type can be detected by "class()" function.
### 🔴 Numeric Data
Numeric data represents numbers that can be either decimals or integers. ıt is the default type for numbers in R.
```r
num1 <- 47
num2 <- 6.79

class(num1)
class(num2)
```
```r
# Given functions can be used for numeric data. Remind that not all functions are listed below. You can always check literature for more examples.

# - +,-,*,/ --> addition, subtraction, multiplication, division
10+2
4*9

#abs() --> absolute value
abs(-4)

#sqrt() --> square root
sqrt(81)

#round() --> round the nearest decimal or integer
round(4.8267, 2)
round(4.8267)
```
### 🟠 Integer Data
Integer data describes set of integers stored in a variable. They are represented with a capital "L" at the end of the number. Numeric data can be converted to Integer data via "as.() function".
```r
int1 <- 7L
int1
class(int1)

num <- 22
class(num)
is.integer(num)

num <- as.integer(22)
class(num)
```
### 🟡 Complex Data
Complex data describes set of complex numbers stored in a variable.
```r
comp <- 4i+36
class(comp)
```
### 🟢 Character Data
Character data represents texts or words enclosed in quotation marks ("). It can store strings which involves alphabets, numbers, and symbols. 
```r
word <- "apple"
sentence <- "I eat apple."

class(word)
class(sentence)
```
Strings can be converted to numeric data via "as.() function" if it composed of numbers
```r
str <- "100"
class(str)
is.character(str)

num <- as.numeric(str)
class(num)
is.character(num)
```
```r
# Given functions can be used for character data. Remind that not all functions are listed below. You can always check literature for more examples.

# nchar() --> counts number of characters
nchar("apple")

#toupper() --> converts to uppercase
toupper("apple")

#substr() --> extracts a given part of the string
substr("apple", 2, 4)

#paste() --> combines strings together
paste("apple", ", banana")
```



