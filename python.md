#Python

## issues
* `No module named 'pytest'`
	* check the filename for example, `test_xxx.py` it will happends this problems, try to not use the file name begin with `test_`

## Moudle
* python module: tdqm （taqaddum） -> used for Task completion bar
* python module: random
	* get a random number from (0,1): `random.random()`
	* choose one random choice from a list:
```python
a = [1,2,3,4,5]
random.choice(a)
# 2
```
	* choose k random choices from a list:
```python
b = [3,4,1,2,3,7]
random.choices(b, k=3)
# [3,3,2]
```

## Other usage

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

* when you defined a function in a class named `__build_network`, that means it is a private method of class, the other modules could not access, for example: ...

## Class
```python
class Persion:
    def __init__(self, name='Persion'):
        self.name = name
class Puple(Persion):
    pass
class Puple_Init(Persion):
    def __init__(self, age):
        self.age = age
class Puple_Super(Persion):
    def __init__(self, name, age):
        self.age = age
        super().__init__(name)
```
* `super().__init__()`: it was used to inherit the class `Persion` and init the `self.name`
