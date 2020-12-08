#Python


## miniconda
* create virtual env: `conda create -n tensorflow2 python=3.6`
* set config: for mac:
```shell
vim ~/.condarc
```
```shell
channels:
show_channel_urls: true
channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - defaults
allow_conda_downgrades: true
```


## issues
* `No module named 'pytest'`
	* check the filename for example, `test_xxx.py` it will happends this problems, try to not use the file name begin with `test_`

## Moudle
* python module: tdqm （taqaddum） -> used for Task completion bar
* python module: random
	* get a random number from (0,1): `random.random()`
	* choose one random choice from a list:

* optparse
	
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
* numpy
	* `a = np.expand_dim(a, axis=1)` : `axis` represents the add position and add in the left hand


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

* `with open('file_path') as :`
	* 'a': open and add the things following the end
	* 'w': overwrite
	* you can pass `encoding='utf-8'` if you want to read str in chinese

* yield
```python
def foo():
    print('yes')
    a = [1, 2, 3, 4, 5, 6]
    for i in a:
        yield i
        print('no')

g = foo()
```
* when a function use yield to return, `g = foo()` will execute and return nothing unless `next(g)`:
```python
next(g) # yes 1
next(g) # no 2
next(g) # no 3
```

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

## read xml file
```python
	import xml.etree.ElementTree as ET
    tree = ET.parse(annotation_path + image_annotation_name[i])
    root = tree.getroot()
```
* `for child in root.iter('object'):`, `child.find('name').text`, `child.tag` and `child.text`

## matplotlib
* `plt.firgure()`:
* `plt.subplot(221)`: `2`, nrows, `2`, ncols `1`, number of subplot

## opencv
* convert to gray image: `gray = cv2.cvtColor(img_path, cv2.COLOR_BGR2GRAY)`
* remains specified color:
```python
#blue
low_hsv = np.array([100,43,46])
high_hsv = np.array([124,255,255])
mask = cv2.inRange(hsv,lowerb=low_hsv,upperb=high_hsv)
```
* Canny edge detection:
```python
img = cv2.GaussianBlur(mask,(3,3),0)
canny = cv2.Canny(img, 50, 150)
```
* find boundingbox
```python
contours, hierarchy = cv2.findContours(mask, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)
for c in contours:
    x, y, w, h = cv2.boundingRect(c)
    area = w * h
    if (area > 2500):
        if max(w, h) / min(w, h) < 2:
            boundingBoxlist.append([x, y, w, h])
            imgToAdd = img[y:y + h, x:x + w]
            testList.append(imgToAdd)
            cv2.rectangle(img, (x, y), (x + w, y + h), (0, 0, 255), 3)
```
