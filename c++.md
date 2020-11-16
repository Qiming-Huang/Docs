# C++

* how c++ compiled
	* some aspects: `C++ source file `, `Preprocess`, `Compile`, `Link`, `object file`, `header files`, 
		* a c++ source file : `.cpp, .cxx or .cc extension suffixes.`
		* header files : `#include`, have extensions like `.h, .hpp, or .hxx`
* list
creat and assign: `int n[2] = {1,2};`， can also, `int n[] = {1,2,3,4,5,6};`
```c++
int n[] = {1,2,3};
int *p = n;
p[3] = 4;
cout << p[3];
// 4
```

## function
* `sizeof()`:return a memory which a object or type took.
	* for example, `int a[] = {1,2,3}`, `sizeof(a)` returns 12, `sizeof(a[0])`returns 4 (because a int cost 4 bits)
	* return the length of a list `sizeof(a)/sizeof(a[0])`


