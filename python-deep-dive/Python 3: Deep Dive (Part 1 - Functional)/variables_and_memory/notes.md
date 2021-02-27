### Variables and Memory References.

- Variables `are` memory references.
- We can think of `memory` as a series of boxes or `slots` that exist on our computer.
- We can store and retrieve data from these `slots`.

- For each `slot` in memory, we have to have a unique address associated with that slot.
- Just like with mailboxes, each package (data) you physically send to an address, has a unique mailbox associated with that address.
- In computing, those addresses are called `memory addresses` that point to a specific `slot` in our memory.
- When storing data in in memory slots, these memory slots can hold a finite amount of data, and depending on the object you insert into that slot. That object can span through multiple slots (memory addresses).
- The objects stored in these `slots` at these `memory addresses` wether they span one slot or three. All of those objects are reffered to in python as the `Heap` which is managed by something called the `Python Memory Manager`

#### Refrences

When you assign a variable to a value ex: `var_1 = 10` `var_1` becomes a reference to the memory address associated with the object 10, the variable name is NOT the memory address itself, rather a reference to the memory address to the slot that holds the value 10.

To get the memory address of that variable name, you can use the Python built in `id` function.
The `id` function will give you a Base-10 number that you can then convert to `hex` or whatever other format you'd like.

Let's write some code to better understand this.

```
var_1 = 10 
print(id(var_1)) # 4402870864 (Base-10)
print(hex(id(var_1)) # 0x1066e7a50 (Hexedecimal representation of the memory address)
```
Let's print out the variable and explain what happens.

```
print(var_1)
```

Python get's the memory reference for var_1, retrieves the value stored at that memory address slot and gives us back a value to use in our code.


In the end, variables are not what we think we are. Logically we can think that var_1 is simply euquals to 10 and we should think that way. But variable names are just a means for python to get the memory address to that `slot` in the `heap`.
