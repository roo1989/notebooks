### Reference Counting

#### Notes
- Variables are just pointers to a memory addres.
- To keep track of how many objects are stored at that memory adderss, we use the term `reference counting`
- Let's say that we have a `variable_1` that points to `variable_0` then we have one memory address, but two references to that memory address.


#### Examples
```
my_var = 10

print(id(my_var)) # -> 4339206736

```
| reference | count |
|--|--|
| 4339206736 | 1 |

```
my_var_2 = my_var

print(id(my_var_2)) # -> 4339206736
```

| reference | count |
|--|--|
| 4339206736 | 2 |

You see what happens here - I assign a variable my_var, with a value of 10.
In other words, I store the integer object 10 to a `slot` in the memory with the memory reference of `4339206736`

Next up, I assign a variable my_var_2 and point it to my_var_1.
In other words, I create another variable and assign it to the same `memory reference` as `my_var` which is `4339206736`
Therefor, the reference count for that memory address goes from one to two.

Again, let's change things up.
```
my_var = None
```

Now, the reference count from `4339206736` goes from two to one.

So let's say that the other variable `my_var_2` goes away, out of scope or is reassigned to a difference memory address. The reference count for `4339206736` goes down to zero.

In this case, the `Python Memory Manager` simply throws that reference to that memory address away. We as programmers do not have to think about it or de allocate the memory object. Python does that for us.

#### Finding the reference count.

#### sys.getrefcount(var)
In Python, there are a few ways we can get the reference count from a variable.
First one, is from the [sys](https://docs.python.org/3/library/sys.html) module in Python and it's a function called `sys.getrefcount(my_var)`.

This approach has a drawback in the sense that it creates another reference to the variable since we are passing `my_var` as an argument to the function. So the count of that reference will increase by one when calling that method.

```
import sys

a = [1, 2, 3]
print(id(a)) # -> 4532967808
sys.getrefcount(a) # -> 2
```
| reference | count |
|--|--|
| 4532967808 | 2 |

In theory, the reference count of `a` should be 1. But simply the act of passing a as an argument function to `getrefcount(a)` creates another reference. Keep that in mind if you ever find yourself in a situation where you need to find the count of a memory reference.

##### ctypes.c_long.from_address(address).value

This is another way to get the reference count **without** increasing the reference count.
We are digging into the Python C library here, and we are passing in a value or the `id` of the reference, not the reference itself. Therefor we are not going to see an increment in the reference count.

I'm going to create a small wrapper function to use as an example of how to use that function.

```
import ctypes
def get_reference_count(address: int):
    return ctypes.c_long.from_address(address).value

print(get_reference_count(id(a)) # Passing in the `id` of the variable, not the reference.
This will return 1.
```
