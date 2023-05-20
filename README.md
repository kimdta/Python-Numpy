# Python-Numpy
From basic to advanced

# 1. Basic Operations on Arrays
a) In NumyPy an array can be created in several different ways. 
Create the one- dimensional array...

- by defining a list and converting it to an array.
```ruby
list = [1, 2, 3, 4, 5]
a = np.array(list)
```
- or using the method “arange”.
```ruby
a = np.arange(1,6)
```
- or slicing and copying out of a second array (that you have to define beforehand).
```ruby
b = np.array([1,2,3,4,5,6,7,8,9])
c = b[0:6]   #exclusive 6th element
print(c)
```
===> [1 2 3 4 5 6]

b) Create the 3-dimensional array a: array([1,2], [3,4], [5,6]) ...

- by defining a list and converting it to an array.
```ruby
list = [[1,2], [3,4], [5,6], [7,8], [9,10]]
a = np.array(list)
print(a)
```
===> [[ 1  2]
     [ 3  4]
     [ 5  6]
     [ 7  8]
     [ 9 10]]

- or defining a second array containing [1,2,3,4,5,6] and reshaping
```ruby
b = np.array([1,2,3,4,5,6])
b = b.reshape(3,2)
print(b)
```
===> [[1 2]
     [3 4]
     [5 6]]

- slicing the first three sub-array
```ruby
b = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]])
b = b[0:3]
print(b)
```
===> [[1 2]
     [3 4]
     [5 6]]
     
c) Create a two-dimensional array with 10 elements each. Elements being random 32bit integers between 1 and 5.

```ruby
a = np.random.randint(1,6, size= (2,10), dtype= np.int32)     #size(2 dimensional, 10 elements each)
print(a)
#print the first sub-array 
print(a[0])   
#print the third value of second sub-array
print(a[1,2])   #(sub-array, the value position)
```
# 2. Advanced Operations on Arrays

Define an array with elements being every number in the range from 0 to 20 in ascending order
```ruby
x = np.arange(0,21)
print(x)   ---> [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]

#Add 4 to every elements using corresponding element-wise operation
x = x +4
print(x)   ---> [ 4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24]

#Find the smallest, largest, mean of all the values
print(x.min())  ---> 4
print(x.max())  ---> 24
print(x.mean()) #print(np.mean(x)) works the same ---> 14.0

#Define a second array with the equal number of elements and calaculate the scalar product of the 2 arrays
y = np.arange(-3, 18)
print(y)  ---> [-3 -2 -1  0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17]

#Scalar product of x and y
print(x*y) ---> [-12 -10  -6   0   8  18  30  44  60  78  98 120 144 170 198 228 260 294 330 368 408]

#Matrices multiplication
print(np.dot(x,y)) ---> 2828
#or
print(np.matmul(x,y))
#or
print(np.sum(x*y))

#CAUTION: dot() and matmul() only used in 2D array
```
# 3. Translating formula

a) Solve system of linear equations: (i) 2x + 3y = 15 (ii) 1x + 6y = 18

```ruby
a = np.array([[2,3],[1,6]])
b = np.array([15, 18])  

r = np.linalg.solve(a, b)   # a is array of parameters contained n sub-arrays (n equations)
print("x = " + str(r[0]) + ", y = " + str(r[1]))
```
===> x = 4.0; y = 2.3333333333333335

b) Write a small program that given the length of 2 legs, calculate the length of the hypotenuse of a rectangular triangle

```ruby
leg1 = np.array([int(input("Enter leg 1: "))])
leg2 = np.array([int(input("Enter leg 2: "))])
print(np.sqrt(leg1**2 + leg2**2))

#Alternative
while True:

     a = input("Enter leg 1: ")
     if a == "q":
         break
     b = input("Enter leg 2: ")
     if b == "q":
         break
     c = np.sqrt(np.power(int(a), 2) + int(b)**2)
     print("c = " + str(c))
```
===> Enter leg 1: 3; Enter leg 2: 4; [5.]

c) Calculates the shortest distance from (0,0,0) to any point(x,y,z) in 3D space
Remind: Distance = sqrt(|x2-x1|^2 + |y2-y1|^2 + |z2-z1|^2)

```ruby
a = np.array([0, 0, 0])
b = np.array([int(input("x: ")), int(input("y: ")), int(input("z: "))])

#Distance
r1 = np.sqrt(np.sum((np.absolute(a-b))** 2))
print("Disance = " + str(r1))

# or
r2 = np.sqrt(np.sum(np.power(a - b, 2)))
print("Disance = " + str(r2))
```
===> x: 3; y: 4; z: 5; Disance = 7.0710678118654755

