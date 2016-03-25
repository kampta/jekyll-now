---
layout: post
title: Parallel processing in python
---

Python's `multiprocessing` module had been a tool of my choice until I came across `pathos`. Here are couple of reasons why

## Why `multiprocessing` in python is broken

There are few problems I face while using existing multiprocessing library in python. Here I am going to discuss two of them which I face very often.
Lets start off with an example of simple usage of the library

```python
def add(x=5, y=1):
	return x+y

from multiprocessing import Pool

p = Pool(4)
inX = range(10)
print p.map(add, inX)
```
```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

Works fine! 

### Problem 1: Passing multiple arguments to a method

But if I want to pass on both `inX` and `inY`, the code breaks:
```
TypeError: unsupported operand type(s) for //: 'int' and 'list'
```

To my surprise, it's not straightforward to pass more than one argument to `Pool.map`. In a simple case of passing multiple arguments to `multiprocessing.Pool.map` method, I have to use a workaround like following

```python
def add(tuple_of_numbers):
	x = tuple_of_numbers[0]
	y = tuple_of_numbers[1]
	return x+y
    
p = Pool(4)
inX = range(10)
inY = range(10)
print p.map(add, zip(inX, inY))
```
```
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```

Its a bit strange how functions are passed to subprocesses using `pickle`. In case, your add function doesn't take default values, there is another work around using `partial`.

```python
from functools import partial
    
def add(x,y):
	return x+y
    
    
p = Pool(6)
partial_add = partial(add, y=1)
inX = range(10)
print p.map(partial_add, inX)
```
```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Problem 2: Parallelizing a method within a class

More problems come when you are trying to parallelize a method within your class

```python
from multiprocessing import Pool
    
class myClass:
	def __init__(self):
		pass
    
	def square(self, x):
		return x*x
    
	def run(self):
    		p = Pool(processes=4)
		return p.map(self.square, range(10))


if __name__== '__main__' :
	m = myClass()
	print m.run()
```
```
PicklingError: Can't pickle <type 'instancemethod'>: attribute lookup __builtin__.instancemethod failed
```
For static methods, there is a bit dirty get around

```python
from multiprocessing import Pool

def out_square(arg, **kwarg):
        return myClass.square(*arg, **kwarg)

class myClass:
        def __init__(self):
                pass

        def square(self, x):
                return x*x

        def run(self):
                p = Pool(4)
                inX = range(10)
                return p.map(out_square, zip([self]*len(inX), inX))


if __name__== '__main__' :
        m = myClass()
        print m.run()
```
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

For non-static methods, above problem has been discussed in [stackoverflow](http://stackoverflow.com/questions/1816958/cant-pickle-type-instancemethod-when-using-pythons-multiprocessing-pool-ma). From what I understand, python can pickle standalone references to functions but not class methods. When method exists within a class, you have to provide with extra infrastructure in the class to make the method "pickle-able". One way to do that is to use `copy_reg` described in an answer by **Steven Bethard** [here](http://bytes.com/topic/python/answers/552476-why-cant-you-pickle-instancemethods).

---

I came across [Pathos](https://github.com/uqfoundation/pathos.git), a python parallel processing library from caltech. Since I have stopped using `multiprocessing` module altogether.

## Comes Pathos

In author's language "Pathos is a framework for heterogenous computing. It primarily provides the communication mechanisms for configuring and launching parallel computations across heterogenous resources".

Documentation of the library is bit sparse. So here are some cliff notes on how to quickly start being productive with Pathos.

### Installing

Pathos will require four different packages to be installed. I installed the latest version along with dependencies the following way 
    
    pip install git+https://github.com/uqfoundation/pathos.git@master

### Usage

Let's take a look at simple applications using pathos

```python
def add(x,y):
	return x+y

from pathos.pools import ParallelPool as Pool
p = Pool()

inX = range(10)
inY = range(10)

print p.map(add, inX, inY)
```
```
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```
	
```python
from pathos.multiprocessing import ProcessingPool as Pool

class myClass:
	def __init__(self):
		pass

	def square(self, x):
		return x*x

	def run(self, inList):
		pool = Pool().map
		result = pool(self.square, inList)
		return result

if __name__== '__main__' :
	m = myClass()
	print m.run(range(10))
```
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

## Summary
I highly recommend `pathos` for multiprocessing and making your code fast with few extra lines.
