#Python

* `if __name__ == '__main__':` 
	```
	---test1.py
	---test2.py
	test1.py
		print('This is A')
		if __name__ == '__main__':
			print(This is B)

	test2.py
		import test1
	```
	when we execute `python test1.py`, we get the output
	```
	This is A
	This is B
	```
	Then, we execute `python test2.py`, we get the output
	```
	This is A
	```
	* hence, the `if __name__ == '__main__':` is used for import things, if execute it directly, it will execute the whole thing, but if we import it and execute, if will not execute the codes below `if __name__ == '__main__':`

* when you defined a function in a class named `__build_network`, that means it is a private method of class, the other modules could not access, for example:
```python
from test1 import test
a = test
```


```python
a.test1()
```

    this is a test 1



```python
a.__test2()
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-17-44ad9b8e385b> in <module>
    ----> 1 a.__test2()
    

    AttributeError: type object 'test' has no attribute '__test2'



```python
# In the test1.py
```


```python
# class test(object):
#     def test1():
#         print('this is a test 1')
        
#     def __test2():
#         print('this is a test2')
```


```python
#__test2() is a private method of class test1, you can not access from the out side
```

* in python, `""` and `''` are same, but it's usful when `"This is 'my' book"`