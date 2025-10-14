# Data Structures
Data structures are basically tools to store and organize data so that can be understood by the computer and further, can be processed effectively. 
They can hold various types of values collectively.

## 📘 Vectors
- Vectors are one-dimentional data structures that holds values belonging to the same data type. 
- The index of a vector starts from "1", not "0".
- Vectors are created by **"c()"** funciton and the components of the vectors are seperated by comma (,).
```r
fruits <- c"(banana", "apple", "melon")
# class() --> to determine how R interprets the object.
class(fruits)
# typeof() --> to determine what is stored in the object.
typeof(fruits)
fruits
```
- Vectors can be numeric, character, or logical.
```r
numeric_vec <- c(5, 19, 45)
numeric_2_vec <- c(4L, 16L, 7L)
character_vec <- c("saturn", "uranus", "mars")
logical_vec <- c(TRUE, FALSE)
```
```r
# Given functions can be used with vectors. Note that there are more and more functions available for vector, you can check.

#lenght() --> returns the number of elements.
even_num <- c(2, 4, 6, 8)
lenght(even_num)

#x[i] --> to access a certain elements indicated with its index (i). You can also access multiple elements of a given interval via x[i:i+2]
even_num[1:3]

#append() --> to add new elements to the vector.
new_even_num <- append(even_num, "10")

#sort() --> sorts the elements of the vector.
sort(even_num, decreasing = TRUE)

#You can also use statistical functions such as min(), max(), mean(), sum(), sd() with numeric values.
```
## 📗 Lists
- Lists are one-dimentional data structures that stores data from different types.
- A list can store matrix, vectors, characters...
```r
# Create vectors and variables
studentId <- c(101, 102, 103)
studentName <- c("Ayşe", "Berk", "Cem")
studentGrade <- c("A", "B", "A")
totalStudents <- 3

# Create a list combining all information
studentList <- list(
  "ID" = studentId,
  "Names" = studentName,
  "Grades" = studentGrade,
  "Total Students" = totalStudents
)

print(studentList)

# Access specific component using $
print(studentList$Names)

# Access specific student’s grade
print(studentList$Grades[2])
`




