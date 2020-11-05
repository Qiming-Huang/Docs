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