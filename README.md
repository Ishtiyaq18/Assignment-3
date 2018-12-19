# Assignment-3

#1.1 Write a Python Program to implement your own myreduce() function which works exactly
#like Python's built-in function reduce()

#Defining the function to take the list iteration
def myreduce(func, lst):
    finalValue = lst[0]
    for val in lst[1:]:
        finalValue = func(finalValue,val)
    return finalValue

#Defining function to add numbers
def addnums(x,y):
    c = x + y
    return c

#Defining fuction to multiply numbers
def multiplynums(x,y):
    c = x * y
    return c
    
    #Adding numbers using myreduce function
myreduce(addnums,[18,42,39,54])

#Multiplying numbers using myreduce function
myreduce(multiplynums,[18,42,39,54])

#1.2 Write a Python program to implement your own myfilter() function which works exactly like
#Python's built-in function filter()

#Defining the function
def myfilter(func,lst):
    output = []
    for i in lst:
        if (func(i)):
            output.append(i)     
    return output

#Defining the criteria, in this case its set to filter out numbers less than or equal to 3
def func_filter(num):
    if (num <=3):
        return True

#The result of the function
myfilter(func_filter,[5,2,3,7,1,2,0,-2,0,1])

word = "ACADGILD"
alphabet_list = [ alphabet for alphabet in word ]
print ("ACADGILD = "+str(alphabet_list))

input_list = ['x','y','z']
result = [ item*num for item in input_list for num in range(1,5)  ]
print("['x','y','z'] = "+str(result))

input_list = ['x','y','z']

#Using two different ranges to generate the desired output

result = [ item*num for num in range(1,3) for item in input_list]+[ item*num for num in range(2,5,2) for item in input_list]
print("['x','y','z'] = " +   str(result))

input_list = [2,3,4]
result = [ [item+num] for item in input_list for num in range(0,3)]
print("[2,3,4] = " +  str(result))

input_list = [2,3,4,5]
result = [ [item+num for item in input_list] for num in range(0,4)  ]
print("[2,3,4,5] = " +  str(result))

input_list=[1,2,3]
result = [ (b,a) for a in input_list for b in input_list]
print("[1,2,3] = " +  str(result))

# 3.Implement a function longestWord() that takes a list of words and returns the longest one.

def find_longest_word(words_list):
    word_len = []
    for n in words_list:
        word_len.append((len(n), n))
    word_len.sort()
    return word_len[-1][1]

find_longest_word(['ACADGILD','ASSESSMENT','SCORE'])
