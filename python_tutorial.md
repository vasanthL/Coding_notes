# Python practical notes


```python
print("hello va")
```

    hello va



```python
print("the morning \n is the \n evening of world")
```

# (#)single headings

## (##) Major Headings

# Data Types


```python
a=2 #a is a pointer
```


```python
id(a) #to get the memory location of a
```


```python
type(a) #to find var type
```


```python
print(int(4.555),float(93)) #type conversion
```


```python
print("the common var type in python is : ",56/7,"\nthe operator to find the square is : ",7**2)
```

# Arithmetic Operators


```python
x,y=2,3
print("x =>",x," y=>",y)
```


```python
x,y=y,x #direct swapping is allowed
print("x =>",x," y =>",y)
```

## Procedence of Operators


```python
"""" 
(**) exponentiations
(~+-) plus and unary plus and minus
(* / % //) mul div module floor
(+ -) add sub
(>> <<) right and left bitwise
& bitwise 
(^ |) bitwise or and and
(<= <> >=) comparison operator
(<> == !=) Equality operator
(= %= /= //= -= += *=) assignment operator
(is is not) identity operator
(in not in) membership operator
"""
```


```python
print(5+4*2)
```

    13



```python
print(10/9*3) #same level operate from left to right
```

    3.3333333333333335



```python
str1="twinkle"
```


```python
print(str1)
```


```python
os.getcwd()
```




    'C:\\Python37'




```python
os.chdir("C:\\Python37")
```

# Math Module


```python
import math
print(math.sqrt(2))
```

    1.4142135623730951



```python
math.pi #returns pi value
```




    3.141592653589793




```python
math.factorial(5)
```




    120




```python
math.ceil(-2.99)
```




    -2




```python
math.fabs(-2.99) # returns the absolute value of the number
```




    2.99



# Excercises


```python
print(str(int("5")+int("10")))
```

    15



```python
x,y=5,6
x+=(-2)
print(x)
```

    3


# File IO Functions


```python
f=open("file1.txt",'w')
f.write("first line\n")
f.write("second line\n")
f.write("third line\n")
f.close()
```


```python
f=open("file1.txt",'r')
f.read(2)
```




    'fi'




```python
f.read(6) #reads the next 6 lines of code 
```




    'rst li'




```python
f.seek(0) # brings the cursor back to the first position
```




    0




```python
f.readline() #read the first line
```




    'first line\n'




```python
f.readline() #reads the next line
```




    'second line\n'




```python
f.seek(0) # brings the cursor back to the beginning 
```




    0




```python
f.readlines() # reads all the individual lines and returns a list
```




    ['first line\n', 'second line\n', 'third line\n']




```python
f.seek(0)
```


    ---------------------------------------------------------------------------
    
    ValueError                                Traceback (most recent call last)
    
    <ipython-input-57-16754355c5bd> in <module>
    ----> 1 f.seek(0)


    ValueError: I/O operation on closed file.



```python
for i in f.readlines():
    print(i)
f.close()
```

    first line
    
    second line
    
    third line


​    

## Print Function


```python
# print(value1,value2,...,sep="",end="\n",file=sys.stdout,flush.False)
for i in "vasi Krish":
    print(i,sep=":")
for i in "vasi Krish":
    print(i,end=":")
```

    v
    a
    s
    i
     
    K
    r
    i
    s
    h
    v:a:s:i: :K:r:i:s:h:


```python
for i in ["vasi","bhai","umesh","thilak","yogesh"]:
    print(i,sep=":")
```

    vasi
    bhai
    umesh
    thilak
    yogesh



```python
print("lll","mmm",sep="&")
```

    lll&mmm



```python
l=[1,2,3,4,5]
print(l,sep="#")
```

    [1, 2, 3, 4, 5]



```python
f=open("file1.txt",'w')
for i in range(1,5):
    for j in range(1,5):
        if(j<=i):
            print(j,end="",file=f)
    print("",file=f)
```


```python
f.close()
```


```python
f=open("file1.txt",'r')
f.readlines()

```




    ['1\n', '12\n', '123\n', '1234\n']




```python
import os
os.getcwd()
```




    'C:\\Python37'



## Input Function


```python
input()
```

    how are you?





    'how are you?'




```python
[a,b]=map(int,(input("enter any two numbers ?")).split(" "))
```

    enter any two numbers ?2 3



```python
type(a)
```




    int




```python
type(b)
```

## Help Function and Tab Completion


```python
help(len)
```

    Help on built-in function len in module builtins:
    
    len(obj, /)
        Return the number of items in a container.


​    


```python
print('vasikrish')
```


```python
str1='krish'
```


```python
str1.capitalize()
```




    'Krish'



## Range Function


```python
#creating a new list
list1=list(range(2,50,7))
print(list1)
```

    [2, 9, 16, 23, 30, 37, 44]



```python
tuple1=set(range(2,10))
print(tuple1)
```

    {2, 3, 4, 5, 6, 7, 8, 9}


## Strings


```python
for i in "vasi krish":
    print("=>",i)
    
```

    => v
    => a
    => s
    => i
    =>  
    => k
    => r
    => i
    => s
    => h



```python
str1="this is jupyter notebook"
```


```python
str1[5:16]
```




    'is jupyter '




```python
str1[3:]
```




    's is jupyter notebook'




```python
str1[:7]
```




    'this is'




```python
str1[3:9]
```




    's is j'




```python
str1[1::2] # return all the odd place characters in a string
```




    'hsi uye oeok'




```python
str1[1::4]
```




    'hiueoo'




```python
str1[1]='a' #strings are immutable so its nt to change character
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-17-87bc774ead84> in <module>
    ----> 1 str1[1]='a' #strings are immutable so its nt to change character


    TypeError: 'str' object does not support item assignment


### String cancatenation


```python
a="vasi"
b="krish"
c=a+b
print(c)
```

    vasikrish


### String Replication


```python
print(a*5)
```

    vasivasivasivasivasi



```python
print(c*2)
```

    vasikrishvasikrish


## Formating Strings


```python
s='the value is %d of the %s'%(2,"rider")
```


```python
s
```




    'the value is 2 of the rider'




```python
 s='the name of %s is %s and his number is %s'%("doctor","arjun",709345)
s
```




    'the name of doctor is arjun and his number is 709345'




```python
for i in range(9):
    print('the number is %d'%i)
```

    the number is 0
    the number is 1
    the number is 2
    the number is 3
    the number is 4
    the number is 5
    the number is 6
    the number is 7
    the number is 8



```python
l=[("the number in %d is red"%i) for i in range(9)]
```


```python
l
```




    ['the number in 0 is red',
     'the number in 1 is red',
     'the number in 2 is red',
     'the number in 3 is red',
     'the number in 4 is red',
     'the number in 5 is red',
     'the number in 6 is red',
     'the number in 7 is red',
     'the number in 8 is red']



### using str.format Method



```python
s='my name is {} and my age is {} and my no is {}'.format("vasanth",21.5,179)
print(s)
```

    my name is vasanth and my age is 21.5 and my no is 179



```python
s='the editor that is used is {}'.format("jupyter")
```


```python
s
```




    'the editor that is used is jupyter'



## String Methods

###### object.method()


```python
s="hello world"
print(s.upper())
print(s.lower())
print(s.capitalize())
print(s.count('o'))
print(s.find('l'))
print(s.startswith("h"))
print(s.index('w'))
print(len(s))
print(s.split(' '))
```

    HELLO WORLD
    hello world
    Hello world
    2
    2
    True
    6
    11
    ['hello', 'world']


## Iterating through Strings


```python
count=0
for i in "the tt tea truck String":
    if(i=='t'):
        count+=1
print("the number of t is %d"%(count))
```

    the number of t is 6


## String Membership test


```python
a='vasi krish'
print('si' in a)
print('is' not in a)
```

    True
    False


## Excercises

###  Reverse a String


```python
str1="thunder"
n=len(str1)
for i in range(n):
    print(str1[n-i-1],end="")
```

    rednuht

### Count Words and Characters


```python
str1="name is odd and even"
wordCount,charCount=0,0
for i in str1:
    if(i != ' '):
        charCount+=1
wordCount=len(str1.split(" "))
print("the number of words is %d\nthe number of char is %d"%(wordCount,charCount))
        
```

    the number of words is 5
    the number of char is 16


### Return part of an Input String


```python
str1="ringingse"
strlen=len(str1)
if((strlen%2==1) and (strlen>7)):
    print(str1[(n//2)]+str1[(n//2)+1]+str1[(n//2)+2])
```

    gin


### Returning String with Maximum length


```python
str2="lorem epsumtra of trigger meternal ruby download lingrem"
l=[]
l=str2.split(" ")
print(l)
mi=0
smallStr=""
for i in l:
    if len(i)>mi:
        smallStr=i
        mi=len(i)
for i in l:
    if(len(i)==mi):
        print(i)
    
```

    ['lorem', 'epsumtra', 'of', 'trigger', 'meternal', 'ruby', 'download', 'lingrem']
    epsumtra
    meternal
    download


## Boolean


```python
bool(4==7)
```




    False




```python
(4==7)
```




    False




```python
bool([])
```




    False




```python
bool('')
```




    False



## Lists


```python
lst=[1,2,3,8,9]
print(lst[2])
print(lst[2:])
```

    3
    [3, 8, 9]



```python
##append method
lst.append([1,2,4])
print(lst)
```

    [1, 2, 3, 8, 9, [1, 2, 4]]



```python
##insert
lst.insert(2,"ste")
print(lst)
```

    [1, 2, 'ste', 3, 8, 9, [1, 2, 4]]


### List Methods


```python
##slicing
lst[1:7]
```




    [2, 'ste', 3, 8, 9, [1, 2, 4]]




```python
#slicing in reverse(reversing a list
lst[::-1]
```




    [[1, 2, 4], 9, 8, 3, 'ste', 2, 1]




```python
##list comprehensions
ls2=[x**2 for x in [1,2,3,4,5,63,4]]
```


```python
ls2
```




    [1, 4, 9, 16, 25, 3969, 16]




```python
ls3=[x*5 for x in ls2 if(x<20)]
```


```python
ls3
```




    [5, 20, 45, 80, 80]



### List constructor



```python
list(range(6))
```




    [0, 1, 2, 3, 4, 5]




```python
list("vasi")
```




    ['v', 'a', 's', 'i']



### List Methods


```python
list1=[5,7,9,10,2,5,7,30]
#object.method()
#append
list1.append(4)
list1
list1.append([12,45,32])
list1
```




    [5, 7, 9, 10, 2, 5, 7, 30, 4, [12, 45, 32]]




```python
list1+[1,1,1]
```




    [5, 7, 9, 10, 2, 5, 7, 30, 4, [12, 45, 32], 1, 1, 1]




```python
#extend method
list2=[9,99,999]
list1.extend(list2)
list1
```




    [5, 7, 9, 10, 2, 5, 7, 30, 4, [12, 45, 32], 9, 99, 999, 9, 99, 999, 9, 99, 999]




```python
str3="vasi"
list1.extend(str3)
```


```python
list1=list1[:9]
list1
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-18-670c124d2621> in <module>
    ----> 1 list1=list1[:9]
          2 list1


    TypeError: 'NoneType' object is not subscriptable



```python
list2=[9,0,8]
str2='vasi'
list2.extend(str2)
list2

```




    [9, 0, 8, 'v', 'a', 's', 'i']




```python
#inset method
#list.insert(i,x)
list2.insert(4,-7)
```


```python
list2
```




    [9, 0, 8, 'v', -7, 'a', 's', 'i']




```python
#remove method
list2.remove('i')
list2
```




    [9, 0, 8, 'v', 'a', 's']




```python
#index method
list2.index('a')
```




    4




```python
#pop method - removes last element from the list
list2.pop()
```




    's'




```python
#count method - to count the no of elements
list2.count(8)
```




    1




```python
#more list methods(reverse,copy,sort,clear)
list1=[12,45,33,89,12,10]
```


```python
#sorting a list in ascending order
list1.sort()
list1
```




    [10, 12, 12, 33, 45, 89]




```python
#sorting a list in descending order
list1.reverse()
list1
```




    [89, 45, 33, 12, 12, 10]




```python
#difference between append() and copy()
list1=[1,2,3,4,5,6]
list2=list1
list1.append("la")
print(list1 is list2)
print(list1,"\n",list2)
#both lists remains same
```

    True
    [1, 2, 3, 4, 5, 6, 'la'] 
     [1, 2, 3, 4, 5, 6, 'la']



```python
list1=[1,2,3,4,5,6]
list3=list1.copy()
list1.append("ne")
print(list1 is list3,"\n",list1,"\n",list3)
#values doesnt get changed 
```

    False 
     [1, 2, 3, 4, 5, 6, 'ne'] 
     [1, 2, 3, 4, 5, 6]



```python
#clear() to remove all elements from the list
print(list1)
list1.clear()
print(list1)
```

    [1, 2, 3, 4, 5, 6, 'ne']
    []


## Converting List to String


```python
#format (stringSeperator).join(IterSequence)
listStr=['have','a','good','day']
str1=(',').join(listStr)
str2=(' ').join(listStr)
print(str1,"\n",str2)
```

    have,a,good,day 
     have a good day



```python
listStr2=['hi','this',4]
(" ").join(listStr2)
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-56-7cb96e02b3be> in <module>
          1 listStr2=['hi','this',4]
    ----> 2 (" ").join(listStr2)


    TypeError: sequence item 2: expected str instance, int found



```python
# Nestled List
lst1=[1,2,3,4,5,[6,7,8],9,10]
print(lst1[5][1],lst1[5][2],lst1[5][0])

```

    7 8 6



```python
alpha=['a','b','c','d',['e','f',['g','h','i']],'j','k']
print(alpha[4],"\n",alpha[4][2],"\n",alpha[4][2][2])

```

    ['e', 'f', ['g', 'h', 'i']] 
     ['g', 'h', 'i'] 
     i


## List Aliasing and Cloning


```python
#aliasing is by using append()
lst1=[1,2,3]
lst2=lst1
lst1.append(4)
print(lst1 is lst2)
print(lst1)
print(lst2)
```

    True
    [1, 2, 3, 4]
    [1, 2, 3, 4]



```python
#Cloning is by using copy()
lst3=lst1[:] # or by using copy() method
lst3 is lst1
```




    False



## List Excercises


```python
#multiply elements in a list
inp=[]
inp=list(map(int,(input()).split(" "))) # returns object of type map and can be operated in (for loop)
mul=1
print(type(inp))
print(inp[0])
for i in inp:
    mul*=i
print(mul)

```

    12 13 14
    <class 'list'>
    12
    2184



```python
import numpy
numpy.prod([1,2,3])
```




    6




```python
#remove duplicate elements from a list
ls=set(map(int,input("Enter the list : ").split(" ")))
print(list(ls))
```

    Enter the list : 12 34 54 12 34 23 54 23
    [34, 12, 54, 23]



```python
#create a list using slicing
ls1=['a','b','c','d','e','f']
ls2=[1,2,3,4,5,6]
print(ls1[3:]+ls2[:3])
```

    ['d', 'e', 'f', 1, 2, 3]



```python
#create a list uisng different methods(Cloning)
old_list=['c','c++','java','python']
new_list=old_list[:]
print(old_list is new_list)
#create a new list (aliasing)
old_lst=['c','c++','java','python']
new_lst=old_lst
print(old_lst is new_lst)
```

    False
    True



```python
#adding integer 7 to each element in the list
print(list(map(lambda x:x+7,[-1,-2,-3,-4,-5,-6])))
```

    [6, 5, 4, 3, 2, 1]



```python
#converting a list to string
(' ').join(['this','is','the','word'])
```




    'this is the word'




```python
#Nestled list
lst=[[1,2],[3,4],[5,6]]
for i in lst:
    print(i[0],i[1],sep="\n")
```

    1
    2
    3
    4
    5
    6


## Dictionary


```python
#key value pairs of elements
#mutable and unordered
#can be created using dict() function
dict1=dict([('name','vasi krish'),('age',22),('occupation','programmer')])
dict1
```




    {'name': 'vasi krish', 'age': 22, 'occupation': 'programmer'}




```python
dict1['name']
```




    'vasi krish'




```python
dict2={'name':'umesh','age':21,'occupation':'engineering'}
dict2
```




    {'name': 'umesh', 'age': 21, 'occupation': 'engineering'}




```python
dict2['condition']='corona'
dict2
```




    {'name': 'umesh',
     'age': 21,
     'occupation': 'engineering',
     'condition': 'corona'}




```python
dict1['condition']='normal'
dict1
```




    {'name': 'vasi krish',
     'age': 22,
     'occupation': 'programmer',
     'condition': 'normal'}




```python
dict1['fav_countries']=['paris','netherland','swiz']
```


```python
dict1['fav_countries'][2]
```




    'swiz'




```python
dicto={'Type':{'Immutable':'string','mutable':'list'}}
dicto.items()
```




    dict_items([('Type', {'Immutable': 'string', 'mutable': 'list'})])



## Dictionary Methods


```python
# d.clear() - to clear all elements in dictionary
# d.get(key,default) - returns the value of key if it exists in dictionary
#d.items - retuns list of key value pairass in dict
#d.keys() - returns the list of keys in a dictionary
# d.values() - returns the list of values in a dictionary

dict5=dict([('A1','Fresh Produce'),('A2','Frozen Foods'),('A3','Canned Foods'),('A4','Bakery Foods'),('A5','Diary')])

print(dict5.get('A2')) 
print(dict5.items())
print(dict5.keys())
print(dict5.values())
```

    Frozen Foods
    dict_items([('A1', 'Fresh Produce'), ('A2', 'Frozen Foods'), ('A3', 'Canned Foods'), ('A4', 'Bakery Foods'), ('A5', 'Diary')])
    dict_keys(['A1', 'A2', 'A3', 'A4', 'A5'])
    dict_values(['Fresh Produce', 'Frozen Foods', 'Canned Foods', 'Bakery Foods', 'Diary'])



```python
#if key is not found we can pass optional argument
dict5.get('B7','not found')
```




    'not found'




```python
#Other methods
# d.pop(key,default) removes key from dictionary or else default
#d.popitem() removes key value pair from the dict
#d.update([other]) updates the dict using the list
# del dict[key] to remove key value pair from a dictionary
dict5
```




    {'A1': 'Fresh Produce',
     'A2': 'Frozen Foods',
     'A3': 'Canned Foods',
     'A4': 'Bakery Foods',
     'A5': 'Diary'}




```python
dict5.pop('A4') # removes key and returns value
```




    'Bakery Foods'




```python
dict5.pop('B5','not found')
```




    'not found'




```python
dict5.popitem() #removes the last element from the dict
dict5
```




    {'A1': 'Fresh Produce', 'A2': 'Frozen Foods', 'A3': 'Canned Foods'}




```python
dict5.update([('name','vasi krish'),('age',22),('education','engineering'),('skills',['c','python','js'])])
dict5
```




    {'A1': 'Fresh Produce',
     'A2': 'Frozen Foods',
     'A3': 'Canned Foods',
     'name': 'vasi krish',
     'age': 22,
     'education': 'engineering',
     'skills': ['c', 'python', 'js']}




```python
del dict5['education']
dict5
```




    {'A1': 'Fresh Produce',
     'A2': 'Frozen Foods',
     'A3': 'Canned Foods',
     'name': 'vasi krish',
     'age': 22,
     'skills': ['c', 'python', 'js']}




```python
len(dict5) # to find the length of the dictionary
```




    6



## Dictionary membership operators


```python
# check if keys exist in dict
print('A1' in dict5)
print('A5' not in dict5)
dict6=dict([('B5','nuiro'),('B6','rineo')])
dict5==dict6
```

    True
    True





    False




```python
dict5
```




    {'A1': 'Fresh Produce',
     'A2': 'Frozen Foods',
     'A3': 'Canned Foods',
     'name': 'vasi krish',
     'age': 22,
     'skills': ['c', 'python', 'js']}




```python
for i in dict5.keys():
    print(i)
```

    A1
    A2
    A3
    name
    age
    skills



```python
for i in dict5.values():
    print(i)
```

    Fresh Produce
    Frozen Foods
    Canned Foods
    vasi krish
    22
    ['c', 'python', 'js']



```python
for key in dict5:
    print(key,sep=" => ")
```

    A1
    A2
    A3
    name
    age
    skills



```python
for x,y in [(1,2),(3,4),(5,6)]:
    print(x," => ",y)
```

    1  =>  2
    3  =>  4
    5  =>  6



```python
for key,value in list(dict5.items()):
    print(key," => ",value)
```

    A1  =>  Fresh Produce
    A2  =>  Frozen Foods
    A3  =>  Canned Foods
    name  =>  vasi krish
    age  =>  22
    skills  =>  ['c', 'python', 'js']


## Excercises


```python
ex_dict1=dict([(1,1),(2,4),(3,9),(4,16),(5,25)])
for key,value in ex_dict1.items():
    print(key," square is ",value)
```

    1  square is  1
    2  square is  4
    3  square is  9
    4  square is  16
    5  square is  25



```python
## Student Dictionary
Student_Dict1=dict([(1,'Tom'),(2,'Sam'),(3,'Kevin'),(4,'Eric'),(5,'John')])
Student_Dict2={}
for key,value in list(Student_Dict1.items()):
    Student_Dict2[key]=value
    del Student_Dict1[key]
    print(Student_Dict1.items()," => ",Student_Dict2.items())
print(Student_Dict1,"\n",Student_Dict2)
```

    dict_items([(2, 'Sam'), (3, 'Kevin'), (4, 'Eric'), (5, 'John')])  =>  dict_items([(1, 'Tom')])
    dict_items([(3, 'Kevin'), (4, 'Eric'), (5, 'John')])  =>  dict_items([(1, 'Tom'), (2, 'Sam')])
    dict_items([(4, 'Eric'), (5, 'John')])  =>  dict_items([(1, 'Tom'), (2, 'Sam'), (3, 'Kevin')])
    dict_items([(5, 'John')])  =>  dict_items([(1, 'Tom'), (2, 'Sam'), (3, 'Kevin'), (4, 'Eric')])
    dict_items([])  =>  dict_items([(1, 'Tom'), (2, 'Sam'), (3, 'Kevin'), (4, 'Eric'), (5, 'John')])
    {} 
     {1: 'Tom', 2: 'Sam', 3: 'Kevin', 4: 'Eric', 5: 'John'}


## Tuples


```python
## ordered,immutable,faster than list
l,l1,l2,l3=(1,2,3,4,5),(),(9),(8,)
print(type(l))
print(type(l1),type(l3),type(l2))
```

    <class 'tuple'>
    <class 'tuple'> <class 'tuple'> <class 'int'>


### Initialising Many Variables in a Single Row


```python
a=b=c=d=9
print(a,b,c,d)
a1,a2,a3,a4=1,2,3,4
print(a1,a2,a3,a4)
```

    9 9 9 9
    1 2 3 4



```python
tpl1=(1,2,3,4,[5,6,7,8])
print(tpl1,tpl1[2],tpl1[4],tpl1[-1],tpl1[:4],sep="\n")
```

    (1, 2, 3, 4, [5, 6, 7, 8])
    3
    [5, 6, 7, 8]
    [5, 6, 7, 8]
    (1, 2, 3, 4)



```python
#lists in tuple are mutable
tup1=tpl1
tup2=('vasi','krish','rio','professor')
tup3=()
tup1[4][0]=9
print(tup1)
```

    (1, 2, 3, 4, [9, 6, 7, 8])


## Tuple Methods


```python
# all() - returns true if all elements of tuple are true
# any() - returns true if any elements are true.if empty returns false
# len() - returns the length
# max() - returns the largest item in the tuple
# min() - returns the min element in the tuple
tup5=(0,1,2,3)
print(all(tup5),any(tup5))
print(all(tup3),all(tup1),sep="\n")
```

    False True
    True
    True



```python
print(max(tup5),max(tup1))
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-59-2ca1aab91a71> in <module>
    ----> 1 print(max(tup5),max(tup1))


    TypeError: '>' not supported between instances of 'list' and 'int'



```python
print(min(tup5),min([55,3,4,6,]))
```

    0 3



```python
## sum used to calculate sum of tuple elements, tuple() to convert to tuple
print(tuple([1,2,34]),sum((1,2,34)),sep="\n")
```

    (1, 2, 34)
    37



```python
print(tuple("vasi krish"))
```

    ('v', 'a', 's', 'i', ' ', 'k', 'r', 'i', 's', 'h')



```python
## index(),count() = finds index and counts
#tup5.index(1)
tup5.count(1)
```




    1



## Packing and Unpacking Tools


```python
x,y=2,3
print(x,y,sep=" ")
```

    2 3



```python
a='vasi',24,7.9,['c','java','python','javascript']
print(a)
```

    ('vasi', 24, 7.9, ['c', 'java', 'python', 'javascript'])



```python
name,age,cgpa,skills=a
print(name,age,cgpa,skills,sep="\n")
```

    vasi
    24
    7.9
    ['c', 'java', 'python', 'javascript']



```python
x,y=2,3
x,y=y,x
print('x => %d'%(x),'y => %d'%y,sep="\n")
```

    x => 3
    y => 2


## Iterating a Tuple and Operating on Tuples


```python
## membership operator
tup7=(1,2,3,4,5)
print(1 in tup7,7 not in tup7,sep=" = ")
print(((1,2,3,4,5) == tup7),((1,2,3,4,5) is tup7))
print((1,2,3,4) < tup7,(1,2,3,4,5,6)  > tup7)
```

    True = True
    True False
    True True


## Tuple Excercises


```python
tup8=(1,2,3,4,[5,6,7])
tup8[4][0]=9
print(tup8)
```

    (1, 2, 3, 4, [9, 6, 7])



```python
## Unpacking Variables
B=('Mountain View','Santa Clara','California','USA')
a,b,c,d=B
print(a,b,c,d,sep="\n")
```

    Mountain View
    Santa Clara
    California
    USA



```python
##add elements to the tuple.
tup9=(7,9,4,3.3,5)
tup10=('v','a','s','i')
tup9=tup9+tup10
print(tup9)
```

    (7, 9, 4, 3.3, 5, 'v', 'a', 's', 'i')


## Sets


```python
#unordred,no duplicate,iterbale,mutable
#unions intersection
setA={1,2,3,4,[5,6,7,8]} #list cannot be used in sets
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-85-59c759c0df3d> in <module>
          1 #unordred,no duplicate,iterbale,mutable
          2 #unions intersection
    ----> 3 setA={1,2,3,4,[5,6,7,8]}


    TypeError: unhashable type: 'list'


## Set Methods


```python
# add() to add elements to the set
# clear() remove all elements from list
# update() update a set with union of itself and others
# discard() remove an element from set if it is member
# remove() remove an element if not raise key error

setA={1,2,10.0,3,5,7,'python'}
```


```python
setA.add(4)
setA
```




    {1, 10.0, 2, 3, 4, 5, 7, 'python'}




```python
setA.add('Vk')
```


```python
setA
```




    {1, 10.0, 2, 3, 4, 5, 7, 'Vk', 'python'}




```python
setA.update([56,3,4,5,1,2])
setA
```




    {1, 10.0, 2, 3, 4, 5, 56, 7, 'Vk', 'python'}




```python
setB={9,8,99,88}
setA.update(setB)
print(setA)
```

    {1, 2, 3, 4, 5, 99, 7, 8, 9, 10.0, 'Vk', 'python', 56, 88}



```python
#discard to remove an element 
setA.discard(1)
```


```python
#setA.remove(1) provides key error if not found
#setA.discard(1) doesnt proide any error
#setA
len(setA)
```




    13



## SET Methods


```python
# union() return the union of sets in a new set
# intersection() return the inter of two sets in new set
# difference() return the diff of two or more sets as a new set
# symmetric_difference() returns sym_diff of 2 sets in new set
setC,setD={1,2,3,4,5},{2,4,6,8,10}
print(setC.union(setD))
print(setC.intersection(setD))
print(setC.difference(setD))
print(setC.symmetric_difference(setD))
```

    {1, 2, 3, 4, 5, 6, 8, 10}
    {2, 4}
    {1, 3, 5}
    {1, 3, 5, 6, 8, 10}



```python
# pop() remove and return an arbitary set element(1st)
# isdisjoint() return true if two sets have a null intersection
# issubset() return true if another set contains this set
# issuperset() returns true if this set contains another set
#print(setC.pop())
print(setC.isdisjoint(setD))

```

    False



```python
setE,setF={1,2,3},{1,2,3,4,5}
print(setE.issubset(setF))
print(setF.issuperset(setE))
```

    True
    True



```python
1 in setC
```




    True




```python
2 not in setC
#sorted - return a new sorted list from set
setG={33,44,22,11,77}
sorted(setG)
```




    [11, 22, 33, 44, 77]




```python
for i in setG:
    print(i) #produced in unordered sequence
```

    33
    11
    44
    77
    22


## Sets Excercises


```python
setH=set() #initialising a set
print(type(setH))
a=list(map(int,input("Enter the list").split(" ")))
print(type(a))
setH.update(a)
print(setH)
```

    <class 'set'>
    Enter the list1 2 3 4 5 6
    <class 'list'>
    {1, 2, 3, 4, 5, 6}



```python
set_land={'Elephant','lion','crocodile','walrus'}
set_water={'shark','whale','frog','crocodile','walrus'}
print("the union of land and water is ",set_land.union(set_water),sep="\n")
print("the set land that not exist in water",set_land.difference(set_water),sep="\n")

```

    the union of land and water is 
    {'crocodile', 'lion', 'walrus', 'frog', 'shark', 'whale', 'Elephant'}
    the set land that not exist in water
    {'Elephant', 'lion'}


## if Statements


```python
#syntax if(condition): statement
age=2
if (age<5):
    print('Entry free for kids below 5 years')
```

    Entry free for kids below 5 years



```python
age=10
if(age<=5):
    print('entry free')
print('conditon false')
```

    conditon false



```python
flag=' '
if(flag):
    print('proceed')
```

    proceed


## If Elif Else Statement


```python
age=int(input('Enter the age : '))
if(age<=5):
    print('child')
elif (6<=age<=17):
    print('teen')
elif (18<=age<=30):
    print('Youngster')
else:
    print('old person')
```

    Enter the age : 21
    Youngster


## If else Excercises


```python
## to check vowel
a=input('Enter a character : ')
if(a=='a' or a=='e' or a=='i' or a=='o' or a=='u'):
    print('It is a vowel')
else:
    print('It is a consonent')
```

    Enter a character : c
    It is a consonent



```python
## it determine the shape using the sides
side=int(input('Enter the number of sides : '))
shapes=['invalid','invalid','triangle','square','pentagon','hexagon','heptagon','octagon','neptagon','decagon']
if(side<=10):
    print('The shape with %d sides is %s'%(side,shapes[side]))
else:
    print('invalid shape')
```

    Enter the number of sides : 5
    The shape with 5 sides is hexagon


## For Loop


```python
for i in 'python':
    print(i)
```

    p
    y
    t
    h
    o
    n



```python
for i in [1,2,3,4,5]:
    i=i**2
    print(i,end=" ")
```

    1 4 9 16 25 


```python
for i in range(10):
    print(i,end=" ")
```

    0 1 2 3 4 5 6 7 8 9 


```python
## for loop with else
for i in 'python':
    if(i=='t'):
        continue
    print(i,end=' ')
else:
    print('for loop executed successfully')
```

    p y h o n for loop executed successfully


## Nestles Loops


```python
for x in range(1,4):
    for i in 'abc':
        print(i)
    print('----- '+str(x)+' time '+'-----')
    
    
```

    a
    b
    c
    ----- 1 time -----
    a
    b
    c
    ----- 2 time -----
    a
    b
    c
    ----- 3 time -----


## Continue,Break and Pass Statement


```python
b=[3,6,-1,0,1,-2,4,5]
for x in b:
    if(x<0):
        continue
    x=x**2
    print(x,end=' ')
```

    9 36 0 1 16 25 


```python
inp=input("Enter your decision(y/n) : ")
if(inp=='y'):
    print('yes')
elif(inp=='n'):
    print('no')
else:
    pass
```

    Enter your decision(y/n) : 7



```python
## Enhanced loop
[print(x**2,end=" ") for x in range(9)]
```

    0 1 4 9 16 25 36 49 64 




    [None, None, None, None, None, None, None, None, None]



## While Loop


```python
## while(cndt): (statement)
a=int((input('enter the value : ')))
while(a>0):
    print(a,end=' ')
    a-=1
else:
    print('\nLoop executed successfully')
```

    enter the value : 7
    7 6 5 4 3 2 1 
    Loop executed successfully



```python
## while loop with  else 
a=int(input('enter the value : '))
while(a>0):
    if(a==2):
        break
    print(a)
    a-=1
else:
    print('loop not executed completely')# this doesnt print
```

    enter the value : 7
    7
    6
    5
    4
    3


## Loop Excercises


```python
## factorial of a number
a,fact=int(input('Enter the number : ')),1
num=a
while(a>0):
    fact=fact*a
    a-=1
else:
    print('The fact of %d is %d'%(num,fact))
```

    Enter the number : 6
    The fact of 6 is 720



```python
## Generate a Sequence
n=int(input("Enter the input : "))
[print(i*2+1,end=' ') for i in range(n)]
```

    Enter the input : 6
    1 3 5 7 9 11 




    [None, None, None, None, None, None]




```python
## Find the sum of all integers entered by the user
sum_n=0
while(True):
    n=int(input('Enter a int : '))
    if(n==0):
        break
    sum_n+=n
print('The sum of integers is : %d'%sum_n)
```

    Enter a int : 1
    Enter a int : 2
    Enter a int : 3
    Enter a int : 4
    Enter a int : 5
    Enter a int : 6
    Enter a int : 7
    Enter a int : 8
    Enter a int : 9
    Enter a int : 0
    The sum of integers is : 45



```python
## Nestled Loops
num=int(input('Enter the value : '))
for i in range(num):
    for j in range(num):
        print('*',end='')
    print('')
```

    Enter the value : 5
    *****
    *****
    *****
    *****
    *****


## Functions


```python
# fnctions may or maynot have a name 
"""
  def func_name(arg1,arg2,...argn):
     statement1
     statementn
  print('outside function')
"""
```




    '\nfemfseefnsf\n'




```python
def greet():
    print('welcome home :)')
#greet()
def add(a,b):
    return(a+b)
def add_print(a,b):
    print(a+b)
add_print(2,add(2,6))
```

    10



```python
#using lists
def prod(lst):
    prod=1
    for i in lst:
        prod*=i
    return prod
lst=map(int,input("Enter the values in list : ").split(' '))
print(prod(lst))
```

    Enter the values in list : 5 6 7 1 1
    210



```python
#using dictionary in list
def value_sum(dict1):
    sum1=0
    for i in list(dict1.values()):
        sum1+=i
    return sum1
dict1=dict([('vasi',90),('umi',92),('thilk',89),('bhai',99)])
print(value_sum(dict1))
```

    370


## Return Statement


```python
def signal(flag):
    if(flag=='green'):
        return('proceed')
    elif(flag=='yellow'):
        return('wait')
    elif(flag=='red'):
        return('stop')
    else:
        pass
signal('red')
```




    'stop'




```python
def misc(a,b):
    return(a/b,a//b,a%b)
div,quo,rem=misc(46,5)
print(div,quo,rem,sep=" ")
```

    9.2 9 1


## Parameter Vs Argument


```python
# param variable in which argument might be passed def add(a,b)
# arg data passed into the function (a,b)

```

## Passing Argument


```python
def student_info(name,age,grade,marks):
    print('name: ',name)
    print('age: ',age)
    print('grade: ',grade)
    print('marks: ',marks)
#student_info('vasi',21,'a',90)
student_info(grade='a',age=21,marks=90,name='vasi')
```

    name:  vasi
    age:  21
    grade:  a
    marks:  90



```python
def stdent_info(name='vasi',age=21,grade='a',marks=98):
    print('name: ',name)
    print('age: ',age)
    print('grade: ',grade)
    print('marks: ',marks)
stdent_info('ruddr',marks=90)
```

    name:  ruddr
    age:  21
    grade:  a
    marks:  90


## Main Functions


```python
 def main():
    def add(a,b):
        return (a+b)
    def sub(a,b):
        return(abs(a-b))
    def mul(a,b):
        return(a*b)
    def div(a,b):
        return(a/b)

main.add(5,4)
```


    ---------------------------------------------------------------------------
    
    AttributeError                            Traceback (most recent call last)
    
    <ipython-input-18-4cc7741c06e0> in <module>
          9        return(a/b)
         10 
    ---> 11 main.add(5,4)


    AttributeError: 'function' object has no attribute 'add'


## Args and Kwargs


```python
# *args is used to pass mul args to a function
# **kwargs is used to pass multiple 'key-value' arguments to a function

def prod(*args):
    prod=1
    for i in args:
        prod*=i
    return(prod)

prod(9,9,9,9,8)

```




    52488




```python
prod(1,2,3,4)
```




    24




```python
def sample(**kwargs):
    print(type(kwargs))
    print(kwargs.items())
    print(kwargs)
sample(a=5,b=0,c=9,d=10)
```

    <class 'dict'>
    dict_items([('a', 5), ('b', 0), ('c', 9), ('d', 10)])
    {'a': 5, 'b': 0, 'c': 9, 'd': 10}



```python
def val(a,b,c,d):
    print('a--',a)
    print('b--',b)
    print('c--',c)
    print('d--',d)
    
var=(44,555,666,77)
val(*var)
```

    a-- 44
    b-- 555
    c-- 666
    d-- 77



```python
def sample2(a,b,c):
    print(a)
    print(b)
    print(c)

dict2={'a':22,'b':77.8,'c':'flot'}
sample2(**dict2)
```

    22
    77.8
    flot



```python
def sample3(a,b,c,d):
    print(a)
    print(b)
    print(c)
    print(d)
    
var=(4,5,7)
sample3('apple',*var)
```

    apple
    4
    5
    7



```python
## format (formal,args,kwargs)

def sample4(a,b,c,d,e,f,g,h):
    print('a--',a)
    print('args--',args)
    print('d--',d,'e--',e)
    print('kwargs--',kwargs)

args=(3,4)
d,e=6,7
kwargs=dict([('f','87'),('g','54'),('h','09')])

sample4(1,*args,d,e,**kwargs)
```

    a-- 1
    args-- (3, 4)
    d-- 6 e-- 7
    kwargs-- {'f': '87', 'g': '54', 'h': '09'}


## Lambda Function


```python
(lambda x,y: x+y) (9,8)
```




    17




```python
(lambda x,y,r: x+2*y-r)(10,3,2)
```




    14




```python
(lambda a,b,c: a-b-c) (10,2,3)
```




    5




```python
a=(lambda x,y:x//y)
a(2,7)
a(5,4)
```




    1



## Map , Reduce and Filter functions


```python
## map syntax (map(function,sequence))
l=[-1,-2,-3,0,4,5,7,8]


```


```python
list(map(lambda x:x>0,l))
```




    [False, False, False, False, True, True, True, True]




```python
l1=[1,2,3,4,5]
l2=[7,8,9,10]
list(map(lambda x,y:x*y,l1,l2))
```




    [7, 16, 27, 40]




```python
reduce()
```


    ---------------------------------------------------------------------------
    
    NameError                                 Traceback (most recent call last)
    
    <ipython-input-17-15d8e45d63e9> in <module>
    ----> 1 reduce()


    NameError: name 'reduce' is not defined



```python
## reduce to iterate through varaiables in a list
from functools import reduce
lst1=[1,1,1,8,2]
prod=reduce(lambda x,y:x*y,lst1)
print(prod)
```

    16



```python
# to return max value in the list
from functools import reduce
lst2=[44,2,2,5,99,12]
max2=reduce(lambda x,y:x if x>y else y,lst2)
print(max2)
```

    99



```python
# returns a list of value passing the conditon
lst3=[2,4,22,55,3,4,7,6,6,7]
even3=filter(lambda x:x%2==1,lst3)
print(even3)
print(list(even3))
```

    <filter object at 0x000002E1B92B90C8>
    [55, 3, 7, 7]



```python
#map function applies func to all the variables in list
lst4=[3,2,4,5,6,77,54,33,5,5]
even4=map(lambda x:x%2==0,lst4)
print(even4)
print(list(even4))
```

    <map object at 0x000002E1B92BEFC8>
    [False, True, True, False, True, False, True, False, False, False]


## Scope of Variables


```python
b=6

def func1():
    print (b)
    b=7
    print (b)

func1()
print (b)
```


    ---------------------------------------------------------------------------
    
    UnboundLocalError                         Traceback (most recent call last)
    
    <ipython-input-37-d1867669a802> in <module>
          6     print (b)
          7 
    ----> 8 func1()
          9 print (b)


    <ipython-input-37-d1867669a802> in func1()
          2 
          3 def func1():
    ----> 4     print (b)
          5     b=7
          6     print (b)


    UnboundLocalError: local variable 'b' referenced before assignment



```python
# interpreter searches for a local and then enclosed and then global and then built-in


```

## Function Excercises


```python
def prime(n):
    count=0
    for i in range(1,int(n**0.5)+1):
        if(n%i==0):
            count+=1
    if(count==1):
        return True
    else:
        return False

prime(2)
    
    
```




    True




```python
##using eval function takes the input as an expression

print(eval('9-8'))
print(eval('9*8+5%2'))
```

    1
    73



```python
def math(a,c,b):
    if(c=='+'):
        return(a+b)
    elif(c=='-'):
        return(a-b)
    elif(c=='*'):
        return(a*b)
    elif(c=='/'):
        return(a/b)
    else:
        pass

(a,b,c)=input().split(' ',maxsplit=3)
math(int(a),b,int(c))
```

    9 * 5





    45




```python
import random
print(random.randint(2,8))
print(random.choice(['a','b','c','d']))
```

    8
    b



```python
help(random.choice)
```

    Help on method choice in module random:
    
    choice(seq) method of random.Random instance
        Choose a random element from a non-empty sequence.


​    


```python
# to check if no is closest to random number
import random
print('Too high') if(int(input('Enter a number between 1 to 20 :'))-random.randint(1,20)>0) else print('Too low')
```

    Enter a number between 1 to 20 :10
    Too high


## Object Oriented Programming


```python
# class, object
#syntax
class car:
    def __init__(self,model,brand,year):
        self.model=model
        self.brand=brand
        self.year=year
    def start_engine(self,a,b):
        self.a=a
        self.b=b
        return(self.a*self.b)
    
crv=car(100,'audi',2020)
crv.start_engine(2,4)
```




    8




```python
# Instance and Class attributes
# Class attributes are owned by the class itself
#instance attributes are owned by a specific instance
#instance attribute are specific to an object , class attributes are same for all instances
class car:
    no_wheels=4
    no_objects=1 # class attributes
    def __init__(self,model,brand,year):
        self.model=model
        self.brand=brand #instance attributes
        self.year=year
        car.no_objects+=1
    def details(self):
        print(self.model,self.brand,self.year,sep="\n")

crs=car(777,'bugati',2020)
cvr=car(789,'ferrari',2018)
print(crs.no_wheels,crs.no_objects)
print(cvr.details())
```

    4 3
    789
    ferrari
    2018
    None



```python
class student:
    no_students=4
    start_id=101
    def __init__(self,name,age,dob):
        self.name=name
        self.age=age
        self.dob=dob
        student.start_id+=1
    def marks(self,mark1,mark2,mark3):
        self.mark1=mark1
        self.mark2=mark2
        self.mark3=mark3
        return ((self.mark1+self.mark2+self.mark3)/3)

ashok=student('ashok',21,'23-07-98')
ashok_total=ashok.marks(78,92,73)
print(ashok_total,ashok.start_id)
```

    81.0 102



```python
class contact:
    no_students=78
    roll_start=201602160
    def __init__(self,name,age,bench):
        self.name=name
        self.age=age
        self.bench=bench
        contact.roll_start+=1
    def skills(self,skill):
        self.skill=skill
        return (list(self.skill.split(' ')))

vasi=contact('vasi',21.4,'mid')

vasi.skills('c c++ python java script')
```




    ['c', 'c++', 'python', 'java', 'script']



## Defining Classes and Methods in Jupyter


```python
class car1:
    """ Documentation for Car class"""
    no_of_wheels=4
    no_of_objects=0
    def __init__(self,model,brand,year):
        self.model=model
        self.brand=brand
        self.year=year
        car1.no_of_objects+=1
        
    def start_engine(self):
        print("Start Engine")
        
    def detail(self):
        print('model:',self.model)
        print('brand:',self.brand)
        print('year:',self.year)
        
    def emergency(self,airbag):
        if(airbag):
            print('Deploy Airbag')

crs=car1('001','hyundai',2018)
crs.no_of_objects
crs2=car1('002','honda',2019)
crs2.no_of_objects
crs.detail()
print("----------------")
crs2.detail()
```

    model: 001
    brand: hyundai
    year: 2018
    ----------------
    model: 002
    brand: honda
    year: 2019



```python
print(crs.emergency(True))
```

    Deploy Airbag
    None



```python
crs
```




    <__main__.car1 at 0x2e1b9317f08>




```python
crs.emergency(True)
```

    Deploy Airbag



```python
## dir() method to list the methods and variables of a class
dir(car1)
car1.__doc__ ## return doc for class
```




    ' Documentation for Car class'




```python
car1.__doc__
```


```python
## dict attribute list the attributes and the corresponding values
car1.__dict__
```




    mappingproxy({'__module__': '__main__',
                  '__doc__': ' Documentation for Car class',
                  'no_of_wheels': 4,
                  'no_of_objects': 2,
                  '__init__': <function __main__.car1.__init__(self, model, brand, year)>,
                  'start_engine': <function __main__.car1.start_engine(self)>,
                  'detail': <function __main__.car1.detail(self)>,
                  'emergency': <function __main__.car1.emergency(self, airbag)>,
                  '__dict__': <attribute '__dict__' of 'car1' objects>,
                  '__weakref__': <attribute '__weakref__' of 'car1' objects>})




```python
crs.__dict__

```




    {'model': '001', 'brand': 'hyundai', 'year': 2018}




```python
crs2.__dict__
```




    {'model': '002', 'brand': 'honda', 'year': 2019}



## Inheritance


```python
# Tehnique of building a new class from an existing class
class basic_cake:
    def __init__(self,flour,sugar,butter,eggs):
        self.flour=flour
        self.sugar=sugar
        self.butter=butter
        self.eggs=eggs
        
    def procedure(self):
        print('Mix in '+self.flour+self.sugar+self.butter+self.eggs)

rosebee=basic_cake('flour ','sugar ','butter ','eggs')
rosebee.procedure()

```

    Mix in flour sugar butter eggs



```python
class choco_cake:
    def __init__(self,flour,sugar,butter,coco,eggs):
        self.flour=flour
        self.sugar=sugar
        self.butter=butter
        self.coco=coco
        self.eggs=eggs
        
    def procedure(self):
        print('Mix in '+self.flour+self.sugar+self.butter+self.eggs+self.coco)

chocobee=choco_cake('flour ','sugar ','butter ','coco ','eggs ')
chocobee.procedure()
```

    Mix in flour sugar butter eggs coco 



```python
class berry(basic_cake):
    def __init__(self,flour,sugar,butter,eggs,berry):
        self.berry=berry
        super().__init__(flour,sugar,butter,eggs)
    
    def details(self):
        super().procedure()
        print('berry is:',self.berry)

strawberry=berry('flouuuuuur ','sigar ','butler ','eggs ','strawberry')
strawberry.details()
```

    Mix in flouuuuuur sigar butler eggs 
    berry is: strawberry



```python
class school:
    def __init__(self,school_name,location):
        self.school_name=school_name
        self.location=location
    def sdetails(self):
        print('school name:',self.school_name)
        print('location: ',self.location)

class tour:
    def __init__(self,detour):
        self.detour=detour
        
class teacher(school,tour):
    def __init__(self,tname,subject,school_name,location,detour):
        super().__init__(school_name,location,detour)
        #super().__init__(detour)
        self.tname=tname
        self.subject=subject
    def detail(self):
        super().sdetails()
        print('tname:',self.tname)
        print('subject:',self.subject)
  

```


```python
anju=teacher('grace','tnr','anju kurian','social','queensland')
anju.detail()
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-273-f94589f7861d> in <module>
    ----> 1 anju=teacher('grace','tnr','anju kurian','social','queensland')
          2 anju.detail()


    <ipython-input-272-cceeac49c730> in __init__(self, tname, subject, school_name, location, detour)
         13 class teacher(school,tour):
         14     def __init__(self,tname,subject,school_name,location,detour):
    ---> 15         super().__init__(school_name,location,detour)
         16         #super().__init__(detour)
         17         self.tname=tname


    TypeError: __init__() takes 3 positional arguments but 4 were given



```python
class a(object):
    def __init__(self,vara,*args,**kwargs):
        super(a,self).__init__(*args,**kwargs)
        self.vara=vara
    
class b:
    def __init__(self,varb):
        super(b,self).__init__(*args,**kwargs)
        self.varb=varb
        
class c(a,b):
    def __init__(self,vara,varb):
        super(c,self).__init__(vara=vara,varb=varb)
        print(self.vara,self.varb)
    
```


```python
calc=c('vasi','krish')
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-228-27fb9b6fe5f7> in <module>
    ----> 1 calc=c('vasi','krish')


    <ipython-input-227-ded394718bde> in __init__(self, vara, varb)
         11 class c(a,b):
         12     def __init__(self,vara,varb):
    ---> 13         super(c,self).__init__(vara=vara,varb=varb)
         14         print(self.vara,self.varb)
         15 


    <ipython-input-227-ded394718bde> in __init__(self, vara, *args, **kwargs)
          1 class a(object):
          2     def __init__(self,vara,*args,**kwargs):
    ----> 3         super(a,self).__init__(*args,**kwargs)
          4         self.vara=vara
          5 


    <ipython-input-227-ded394718bde> in __init__(self, varb)
          6 class b:
          7     def __init__(self,varb):
    ----> 8         super(b,self).__init__(*args,**kwargs)
          9         self.varb=varb
         10 


    TypeError: object.__init__() takes exactly one argument (the instance to initialize)



```python
class Bar():
    def __init__(self, bar):
        self.bar = bar
        super().__init__()

class Foo():
    def __init__(self, foo='foolis'):
        self.foo = foo
        super().__init__()

class Baz(Bar,Foo):
    def __init__(self, baz,bar,foo):
        self.baz = baz
        Foo().__init__(foo)
        Bar().__init__(bar)
        

```


```python
class rectangle:
    def __init__(self,length,width):
        self.length=length
        self.width=width
    def area(self):
        return self.length*self.width
    def perimeter(self):
        return 2*(self.length+self.width)
    
class square(rectangle):
    def __init__(self,length):
        super().__init__(length,length)
    
car=square(6)
car.perimeter()
```




    24




```python
class triangle:
    def __init__(self,bas,height):
        self.bas=bas
        self.height=height
    
    def tri_area(self,r,h):
        self.r=r
        self.h=h
        return 0.5*self.r*self.h
    
class rightpyra(square,triangle):
    def __init__(self,base,slant_height):
        self.base=base
        self.slant_height=slant_height
        square.length=base
        square.width=slant_height
    
    def area(self):
        base_area=super().area()
        perimeter=super().perimeter()
        return 0.5*perimeter*self.slant_height+base_area
    
```


```python
class root:
    def __init__(self):
        pass
    
    def pat(self):
        print('pat root')

class shape(root):
    def __init__(self,shape,**kwds):
        super().__init__(**kwds)
        self.shape=shape
        print("shape")
    
    def pat(self):
        print('pat shape')
        super().pat()
        
class color(root):
    def __init__(self,color,**kwds):
        super().__init__(**kwds)
        self.color=color
        print("color")
        
    def pat(self):
        print('pat color')
        super().pat()
    
class name(color,shape):
    def __init__(self,name,**kwds):
        super().__init__(**kwds)
        self.name=name
        print('name')
    
    def pat(self):
        print('pat name')
        super().pat()
        
        
v=name(name='vasi',color="red",shape="hexagon")
v.pat()
```

    shape
    color
    name
    pat name
    pat color
    pat shape
    pat root



```python
class rectangle:
    def __init__(self,length,width,**kwds):
        super().__init__(**kwds)
        self.length=length
        self.width=width
        
    def area(self):
        return self.width*self.length
    
    def perimeter(self):
        return 2*(self.width+self.length)

class square(rectangle):
    def __init__(self,side,**kwds):
        super().__init__(length=side,width=side)
        self.side=side
    
    def sq_area(self):
        super().area()
        
d=square(side=4,length=8,width=6)
print(d.sq_area())

```

    None



```python
py=rightpyra(6,7)
rightpyra.__mro__
#py.width=4
pr=rightpyra(7,221)
pr.perimeter()
py.perimeter()
```




    456



## Python Objects


```python
"""
     objects
       / \
      /   \
   var     instances
   arg     attributes
           functions
           methods
           classes
"""
a='d',2,l=[] all are objects
.
```


      File "<ipython-input-77-daffaa0797e6>", line 11
        a='d',2,l=[] all are objects
                       ^
    SyntaxError: invalid syntax



## Polymorphism


```python
2+3
'vasi'+'krish'
[1,2,3]+[4,5,6]
#same operator used for different attributes to perform different functions
```




    [1, 2, 3, 4, 5, 6]




```python
#ability of an object to adapt the code to the type of object it is processing
x=2
y=3
x.__add__(y)
```




    5




```python
a='vasi'
b='krish'
a.__add__(b)
```




    'vasikrish'



## Opertor Overloading


```python
# change the definition of the builtin operators when are applied to user defined types
# eg(__add__,__mul__,__sub__,+,-,*)
[1,2] + [3,4]
```




    [1, 2, 3, 4]




```python
class cart:
    items=[]
    def __init__(self,items):
        self.items=items
    
    def __add__(self,other): #special method i.e.(+)
        return cart (self.items + other.items) # returns cart object
    
    def __mul__(self,other): # to multiply
        return cart(self.items*other.items)
    
    def __str__(self): # denotes name of class i.e.(cart3)
        return('cart({})'.format(self.items)) # retuns the cart3 object
```


```python
cart1=cart('vasi')
cart2=cart(3)

cart3=cart1 * cart2

```


```python
print(type(cart3),cart3,sep="\n")
```

    <class '__main__.cart'>
    cart(vasivasivasi)


## Encapsulation


```python
# bind together dat and function that manipulate the dataa and that keeps both safe from outside interference and misuse
# _a  protected, __a private

class test2:
    
```


      File "<ipython-input-75-b87cb1ede58c>", line 5
        
        ^
    SyntaxError: unexpected EOF while parsing



## Inheritance



```python
class rectangle:
    def __init__(self,length,width,**kwds):
        super().__init__(**kwds)
        self.length=length
        self.width=width
        
    def area(self):
        return self.width*self.length
    
    def perimeter(self):
        return 2*(self.width+self.length)

class cube:
    def __init__(self,n):
        self.n=n
        
    def volume(self):
        return ((self.n)**3)
    
class square(rectangle,cube):
    def __init__(self,side,length,width,**kwds):
        super().__init__(length,width
                        )
        self.side=side
        print(kwds)
        
d=square(side=3,length=8,width=6,n=3)
print(d.length)
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-159-cec47e247a19> in <module>
         25         print(kwds)
         26 
    ---> 27 d=square(side=3,length=8,width=6,n=3)
         28 print(d.length)


    <ipython-input-159-cec47e247a19> in __init__(self, side, length, width, **kwds)
         20 class square(rectangle,cube):
         21     def __init__(self,side,length,width,**kwds):
    ---> 22         super().__init__(length,width
         23                         )
         24         self.side=side


    <ipython-input-159-cec47e247a19> in __init__(self, length, width, **kwds)
          1 class rectangle:
          2     def __init__(self,length,width,**kwds):
    ----> 3         super().__init__(**kwds)
          4         self.length=length
          5         self.width=width


    TypeError: __init__() missing 1 required positional argument: 'n'



```python

class a:
    def __init__(self,a):
        self.a=a
        
class b(a):
    def __init__(self,b,a):
        super().__init__(a)
        self.b=b
B=b('2','5')  
B.a
```




    '5'




```python
class a:
    def __init__(self,a,**kwds):
        self.a=a
        
class b:
    def __init__(self,b,**kwds):
        self.b=b
        
class c(a,b):
    def __init__(self,c):
        self.c=c
        super().__init__(a,b)
 
```

## Encapsulation


```python
# bind together dat and function that manipulate the dataa and that keeps both safe from outside interference and misuse
# _a  protected, __a private

class test2:
    def __init__(self):
        self._a=2
        self.__a=4

t=test2()
print(t._a)
print(t.__a)

```

    2



    ---------------------------------------------------------------------------
    
    AttributeError                            Traceback (most recent call last)
    
    <ipython-input-3-38ecb80eb726> in <module>
          9 t=test2()
         10 print(t._a)
    ---> 11 print(t.__a)


    AttributeError: 'test2' object has no attribute '__a'


## Name mangling


```python
# --x,--function()
class test3:
    def __init__(self):
        self.e=5
        
    def get_attr(self):
        return self.e
    
    def set_attr(self,var):
        self.e=var
        return self.e
    
testcase3=test3()
testcase3.get_attr()
testcase3.set_attr(7)
```




    7




```python
class test4:
    def __init__(self):
        self.__e=6
    
    def get_attr(self):
        return self.__e
    
    def set_attr(self,var):
        self.__e=var
        return self.__e
    
testcase4=test4()
testcase4.get_attr()
testcase4.set_attr(5)
testcase4.__e
```


    ---------------------------------------------------------------------------
    
    AttributeError                            Traceback (most recent call last)
    
    <ipython-input-10-623028e27bc5> in <module>
         13 testcase4.get_attr()
         14 testcase4.set_attr(5)
    ---> 15 testcase4.__e


    AttributeError: 'test4' object has no attribute '__e'



```python
dir(testcase4)
```




    ['__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__',
     '_test4__e',
     'get_attr',
     'set_attr']




```python
# Magic methods in python

class parent:
    def __init__(self):
        self.e=6
        
    def __func(self,var):
        self.e=var
        return ("__func in parent class called,f is{}".format(self.e))
    
class child(parent):
    def __init__(self):
        self.f=3
        super().__init__()
        
    def __func(self,var):
        self.f=var
        return ("__func in child class called,f is {}".format(self.e))
    
c=child()
print(c._child__func(4))
print(c._parent__func(22))
```

    __func in child class called,f is 6
    __func in parent class called,f is22


## Class Methods and Object Method


```python
# class methods are issued to the class and are indicated using a decorator
class library:
    books=['a','b','c','d','e','f']
    
    def __init__(self,student_id,book_title):
        self.student_id=student_id
        self.book_title=book_title
        
    def transaction(self):
        
        return ('Books titled {1} is issued to {0}',self.student_id,self.book_title)
    
    def issue_book(self):
        
        library.books.remove(self.book_title)
        print('list of books available in library {}-->'.format(library.books))
        
    @classmethod
    def add_to_list(cls,new_list):
        
        cls.books+=new_list
        
        print("{0} added to collection".format(new_list))
        return(cls.books)
              
            
```


```python
library.add_to_list(['g','h','i'])
```

    ['g', 'h', 'i'] added to collection





    ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i']




```python
lb=library('vasi','d')
```


```python
lb.transaction()
```




    ('Books titled {1} is issued to {0}', 'vasi', 'd')




```python
lb.issue_book()
```

    list of books available in library ['a', 'b', 'c', 'e', 'f', 'g', 'h', 'i']-->



```python
class rollno:
    id=[101,102,103,104,105]
    
    def __init__(self,name,reg_no):
        self.name=name
        self.reg_no=reg_no
        
    def updated(self):
        print('the roll no of {} is out {} '.format(self.name,self.reg_no))
        
    def id_list(self):
        rollno.id.remove(self.reg_no)
        print('the list of enrolled roles is {} -->'.format(rollno.id))
        
    @classmethod
    def add_list(cls,new_roles):
        cls.id+=new_roles
        print('{} roles are added to the id'.format(new_roles))
        return (cls.id)
    
    
```


```python
ii=rollno('vasi',103)
```


```python
ii.updated()
```

    the roll no of vasi is out 103 



```python
ii.id_list()
```

    the list of enrolled roles is [101, 102, 104, 105] -->



```python
ii.add_list([103,106,107,110])
```

    [103, 106, 107, 110] roles are added to the id





    [101, 102, 104, 105, 103, 106, 107, 110]




```python
class names:
    clss=['vasi','umi','bhai','thilk']
    roll=[101,121,331,213]
    
    def __init__(self,new_name,new_roll):
        self.new_name=new_name
        self.new_roll=new_roll
        
    def update(self):
        print('name {} with roll{} is added'.format(self.new_name,self.new_roll))
        
    def lst(self):
        names.cls.append(self.new_name)
        names.roll.append(self.new_roll)
        print('Cls list is {}'.format(names.clss))
        print('Roll list is {}'.format(names.roll))
        
    @classmethod # decorator that indicates a class method and must be followed by one
    def ad(cls,new_n,new_r):
        cls.clss+=new_n
        names.roll+=new_r
        print('Cls list is {}'.format(cls.clss))
        print('Roll list is {}'.format(cls.roll))
        
    @staticmethod
    def stat(name):
        print('book issued by {}'.format(name))
        
        
```


```python
names.ad(['yogi','sura','sudar','vijay'],[123,454,323,333])
```

    Cls list is ['vasi', 'umi', 'bhai', 'thilk', 'yogi', 'sura', 'sudar', 'vijay']
    Roll list is [101, 121, 331, 213, 123, 454, 323, 333]



```python
## Static Methods
names.stat('name')
```

    book issued by name


## __Str__ and __repr__  method


```python
# __str__ is called using print() or str()
# __repr__ is called using rep()
str(1)
```




    '1'




```python
repr(1)
```




    '1'




```python
str('hello')
```




    'hello'




```python
repr('hello')
```




    "'hello'"




```python
class cart:
    def __init__(self,items):
        self.items=items
    
    def __str__(self):
        return('{0}'.format(self.items))
    
    def __repr__(self):
        return('cart({0})'.format(self.items))
```


```python
cart1=cart(['1',2,3.0])
```


```python
str(cart1)
```




    "['1', 2, 3.0]"




```python
repr(cart1)
```




    "cart(['1', 2, 3.0])"



## Pip


```python
### used to install packages
# pip install yolk3k
# yolk -l to get list of all installed packaged

        

```

## Virtualenv


```python
## allows packages to be installed isolated
# includes seperate (bin, include, libraries.site_packages)
#python -m venv path
# script directory contains the copy of the bin directory
# lib contains site packages
# include is empty
# pyenv.cfg indication of virtual env


```


```python
# to activate a virtualenv
# source path/venv/bin/activate e.g.(C:\python37\venv1\Scripts\activate.bat)
```


```python
# requirements.txt file contains numpy==1.14.3 \n yolk3k==0.9

#pip freeze /path/requirements.txt
# pip install /path/requirments.txt


```


```python
# deactivate is used to close a virtual venv

```

## Modules and Packages


```python
# modules are python file containing definitions and statements (pip.py)
# packages are collection of modules
""" steps involved in importing modules
      1.search for the module
      2.translate all the statement in module to bytecode
      3.Create a module object for the module, initially with a empty namespace
      4.Execute the bytecode, updating the namespace of the module object
      
      
"""


```




    ' steps involved in importing modules\n      1.search for the module\n      2.translate all the statement in module to bytecode\n      3.Create a module object for the module, initially with a empty namespace\n      4.Execute the bytecode, updating the namespace of the module object\n      \n      \n'




```python
# import b as sample
# sample.calc(5,7)
# to import variable from module (from b import var,from b import *) (to use var without using dot notation)

```

## Importing Packages


```python
## Attribute __name__
dir()
```




    ['In',
     'Out',
     '_',
     '_6',
     '__',
     '___',
     '__builtin__',
     '__builtins__',
     '__doc__',
     '__loader__',
     '__name__',
     '__package__',
     '__spec__',
     '_dh',
     '_i',
     '_i1',
     '_i2',
     '_i3',
     '_i4',
     '_i5',
     '_i6',
     '_i7',
     '_i8',
     '_ih',
     '_ii',
     '_iii',
     '_oh',
     'exit',
     'get_ipython',
     'quit']




```python
__name__
```




    '__main__'




```python
# if imported __name__ gets the value of file name

```

## Errors and Exceptions


```python
#two types of errors(suntax and exceptions)
if(2>1) print(True)
```


      File "<ipython-input-12-583d2c815d0c>", line 2
        if(2>1) print(True)
                    ^
    SyntaxError: invalid syntax




```python
if(2>1): print(True)
```

    True



```python
2/0
```


    ---------------------------------------------------------------------------
    
    ZeroDivisionError                         Traceback (most recent call last)
    
    <ipython-input-14-e8326a161779> in <module>
    ----> 1 2/0


    ZeroDivisionError: division by zero



```python
2/7

```




    0.2857142857142857




```python
2/x
```


    ---------------------------------------------------------------------------
    
    NameError                                 Traceback (most recent call last)
    
    <ipython-input-16-e2238fadebef> in <module>
    ----> 1 2/x


    NameError: name 'x' is not defined



```python
'hello'+2
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-17-e95dc495ce41> in <module>
    ----> 1 'hello'+2


    TypeError: can only concatenate str (not "int") to str



```python
list1=[1,2,3]
```


```python
list1[4]
```


    ---------------------------------------------------------------------------
    
    IndexError                                Traceback (most recent call last)
    
    <ipython-input-19-6600837857e0> in <module>
    ----> 1 list1[4]


    IndexError: list index out of range



```python
import Test
```


    ---------------------------------------------------------------------------
    
    ModuleNotFoundError                       Traceback (most recent call last)
    
    <ipython-input-21-a33232ec9687> in <module>
    ----> 1 import Test


    ModuleNotFoundError: No module named 'Test'


## Handling Exceptions


```python
#dealing with exception
"""
   syntax:
       try:
          <statement1>
          <statement2>
        except(Exception type):
            <statement3>
            <statement4>
"""

"""
     Types of errors:
         ZeroDivision Error
         Type Error
         Value Error

"""
```




    '\n     Types of errors:\n         ZeroDivision Error\n         Type Error\n         Value Error\n\n'




```python
a='vasi'
b=6
try:
    result=a+b
    print(result)
except TypeError:
    print('check type of input vasiables')
```

    check type of input vasiables



```python
a=6
b=0
try:
    result=a/b
    print(result)
except(ZeroDivisionError):
    print('denominator  is zero')
```

    denominator  is zero



```python
a,b=2,0
try:
    result=a/b
    print(result)
except(TypeError,NameError,ValueError,ZeroDivisionError):
    print('please check the input variables')
```

    please check the input variables



```python
#to catch all exceptions
a,b=2,'vv'
try:
    print(a/b)
except:
    print('Enter valid integer')
    
```

    Enter valid integer



```python
# a try can have many exceptions
a,b=2,'v'
try:
    print(a/b)
except ZeroDivisionError:
    print('Denominator is zero')
except TypeError:
    print('invalid input type')
finally:
    print('this gets executed always')
```

    invalid input type
    this gets executed always


## DateTime Module


```python
## provides classes and functions to work with times dates and time intervals

"""
imprtant  classes:
Time
Date
DateTime
Timedelta
"""

## timestamp - current time of an event that is recorded by a computer
    
import datetime
```


```python
t1=datetime.time(12,34,45)
```


```python
t1
```




    datetime.time(12, 34, 45)




```python
t2=t1.replace(hour=23)
t2
```




    datetime.time(23, 34, 45)




```python
print(datetime.time.min)
print(datetime.time.max)
```

    00:00:00
    23:59:59.999999



```python
t1.hour
```




    12




```python
t1.second
t1.isoformat()
```




    '12:34:45'




```python
dir(datetime.time)
```




    ['__class__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'dst',
     'fold',
     'fromisoformat',
     'hour',
     'isoformat',
     'max',
     'microsecond',
     'min',
     'minute',
     'replace',
     'resolution',
     'second',
     'strftime',
     'tzinfo',
     'tzname',
     'utcoffset']



## Iterators and Generators


```python
## An object that can be looped over using a loop is called an iterbale
# An iterable has the __iter__ method defined
# Lists,Strings,tuples,sets,dictionaries,files,generators are examples of iterables
list1=[5,10,15,20]

for x in list1:
    print(x**2)
```

    25
    100
    225
    400



```python
dict1=dict([('a',1),('b',2),('c',3),('d',4)])

for x in dict1:
    print(x)
```

    a
    b
    c
    d



```python
list3=[44,55,21]
n=len(list3)
i=0
while(i<n):
    print(list3[i])
    i+=1
```

    44
    55
    21



```python
2 in ['a','b','c']
```




    False




```python
iter(list3)
```




    <list_iterator at 0x2302e953e48>




```python
next(iter(list3))
```




    44




```python
next(iter(list3))
```




    44




```python
# Iterating Through Objects
iter3=iter(list3)
```


```python
next(iter3)
```




    44




```python
next(iter3)
```




    55




```python
list(iter3)
```




    [21]



## How For Loop Actually Works


```python
for i in [1,2,3,4]:
    print(i)
    
"""
    iter_obj=iter(iteraable)
    
    while True:
    try:
        i=next(iter_obj)
    except StopIteration:
        break
    else:
        print(i)
"""
```

    1
    2
    3
    4





    '\n    iter_obj=iter(iteraable)\n    \n    while True:\n    try:\n        i=next(iter_obj)\n    except StopIteration:\n        break\n    else:\n        print(i)\n'




```python
list2=[2,4,6,8]

```


```python
iter2=iter(list2)
while True:
    try:
        item=next(iter2)
    except StopIteration:
        break
    else:
        print(item)
```

    2
    4
    6
    8


## Iteration Protocal


```python
list1=[5,6,7,8]
iter(list1)
```




    <list_iterator at 0x23032787888>




```python
b='bin'
iter(b)
```




    <str_iterator at 0x23032787e88>




```python
iter1=iter(list1)
iter(iter1)==iter1
```




    True



## Generators


```python
## keyword yeild instead return
```


```python
def test():
    print("function begins...")
    x=1
    return(x*2)
```


```python
def test_gen():
    print("function begins...")
    x=1
    yield(x*2)
```


```python
test()
```

    function begins...





    2




```python
t=test_gen()
```


```python
t
```




    <generator object test_gen at 0x00000230326CF448>




```python
next(t)
```

    function begins...





    2




```python
next(t)
```


    ---------------------------------------------------------------------------
    
    StopIteration                             Traceback (most recent call last)
    
    <ipython-input-72-f843efe259be> in <module>
    ----> 1 next(t)


    StopIteration: 



```python
def test2():
    x=1
    yield("the value is {}".format(x))
    x+=1
    yield("the value is {}".format(x))
    x+=1
    yield("the value is {}".format(x))
```


```python
t2=test2()

```


```python
for i in range(0,3):
    print(next(t2))
```

    the value is 1
    the value is 2
    the value is 3


## Arithmetic Sequence


```python
def arith(frst,num,diff):
    count=1
    while(count<=num):
        value=frst+(count-1)*diff
        yield value
        count+=1
        print('count--',count)
        
```


```python
ap1=arith(1,5,3)
```


```python
next(ap1)
```




    1




```python
next(ap1)
```

    count-- 2





    4




```python
next(ap1)
```

    count-- 3





    7




```python
next(ap1)
```

    count-- 4





    10




```python
next(ap1)
```

    count-- 5





    13




```python
next(ap1)
```

    count-- 6



    ---------------------------------------------------------------------------
    
    StopIteration                             Traceback (most recent call last)
    
    <ipython-input-92-fbe1687fcb2a> in <module>
    ----> 1 next(ap1)


    StopIteration: 


## Generator Expression


```python
## lambda - ananymous function
## generator - ananymous gen function

#list comprehension
l=[x**2 for x in range(4)]
print(l)
```

    [0, 1, 4, 9]



```python
#generator expression
gen=(x**2 for x in range(4))
print(next(gen))
```

    0



```python
print(next(gen))
```

    1



```python
print(next(gen))
```

    4



```python
print(next(gen))
```

    9



```python
print(next(gen))
```


    ---------------------------------------------------------------------------
    
    StopIteration                             Traceback (most recent call last)
    
    <ipython-input-102-be0d7584d73f> in <module>
    ----> 1 print(next(gen))


    StopIteration: 



```python

```
