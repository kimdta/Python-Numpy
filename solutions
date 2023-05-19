import numpy as np
#EX2

#a)  Create one dimensional array

#create an array from a list
# list = [1, 2, 3, 4, 5]
# a = np.array(list)
# #or using arange
# a = np.arange(1,6)

# b = np.array([1,2,3,4,5,6,7,8,9])
# c = b[0:6]   #slicing, exclusive 6th element
# print(c)

#b) Create two dimensional array

# list = [[1,2], [3,4], [5,6], [7,8], [9,10]]
# a = np.array(list)
# print(a)
# #define a second array containing [1,2,3,4,5,6] and reshaping
# b = np.array([1,2,3,4,5,6])
# b = b.reshape(3,2) 
# print(b)
# #slicing the first three sub-array
# b = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]])
# b = b[0:3]
# print(b)

#c) Create two-dimensional array. Element being random 32bit integers between 1 and 5

# a = np.random.randint(1,6, size= (2,10), dtype= np.int32)     #size(2 dimensional, 10 elements each)
# print(a)
# #print the first sub-array 
# print(a[0])   
# #print the third value of second sub-array
# print(a[1,2])   #(sub-array, the value position)

# #or
# print(a[1][2])   #2nd sub-array, 3rd value


#EX3
#Define an array with elements being every number in the range from 0 to 20 in ascending order

x = np.arange(0,21)
print(x)
#Add 4 to every elements using corresponding element-wise operation
x = x +4
print(x)

#Find the smallest, largest, mean of all the values
print(x.min())
print(x.max())
print(x.mean())
#or
print(np.mean(x))

#Define a second array with the equal number of elements and calaculate the scalar product of 2 arrays

y = np.arange(-3, 18)
print(y)

print(np.dot(x,y))
#or
print(np.matmul(x,y))
#or
print(np.sum(x*y))
#CAUTION: dot() and matmul() only used in 2D array

#EX4 DATATYPE AND PRECISION

#a) Print the largest 32bit integer and the smallest 64bit float
print(np.iinfo(np.int32).max)
print(np.finfo(np.float64).min)

#b) Execute following codes and expect the result
#a = np.array([2**63 -1])
#print(a)
#print(a+1)

#In python, the int data is signed
z = np.array(np.iinfo(np.int64).max)  #largest positive 01111..1111 represented with 64bit
print(z)

print(z+1) #turn to 1000..00000 smallest negative
#equal to
z= np.array(np.iinfo(np.int64).min)
print(z)

#EX5 Loading and saving Data
#a) Create a 1GB large array filled with 64bit integers between 0 and 99

a = np.random.randint(0, 100, size= (134217728), dtype= np.int64)

np.save("solutions.npy", a)
print(np.load("solutions.npy")[0:4])