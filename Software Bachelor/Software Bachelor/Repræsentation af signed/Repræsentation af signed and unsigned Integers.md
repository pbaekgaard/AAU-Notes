# Signed/Unsigned integers
Integers are normally written as follows:
```C
int x = 13;
int y = -4;
```

When declaring an integer like this, we are essentially declaring a signed integer. The difference between a signed and unsigned integer is that **unsigned integers cannot be negative**.

In the *C* programming-language, integers are by default signed integers. They can be converted into unsigned integers by the same method shown below. 

# Representing negative numbers
There are three ways of representing negative numbers:

## Prefix-bit
Prefix-bit is essentially assigning a bit as an indicator for whether or not it is a negative number.

## Ones' complement
By using Ones' complement we have problems like 0 appearing as both a positive and negative number.

And some standard mathematical rules don't apply like: $a+(-a)\neq 0$

## Two's complement
By using Two's complement we represent negative numbers by the last binary digit being subtracted from the sum. Just like binary, we multiply each 1 and 0 by 2 to the power of the position. Example:
```
10001101 = -115
```

$1*2^0+0*2^1+1*2^2+1*2^3+0*2^4+0*2^5+0*2^6-1*2^7 = -115$


# Converting signed/unsigned integers
When converting signed and unsigned integers we keep the binary representation of the numbers and directly read it as the other.

Fx. 1001 in Two's complement would be -7. Converting this into an unsigned integers we get 9.

![[Pasted image 20230215085152.png]]

![[Pasted image 20230215085604.png]]

![[Pasted image 20230215085630.png]]

![[Pasted image 20230215090213.png]]
The reason the last evaluation is the signed being the bigger number, is because 2147483648U is being typecasted into an integer and therefore a signed integer. Though the number looks bigger, converting 2147483648U into a signed integer, we get the number -1, therefore it is smaller and the left side is therefore greater.


# Problems with unsigned integers
In UNIX there was a problem in which it was possible to access more than allowed from the kernel. This was done by using a negative number in a function that used unsigned integers. The negative number was therefore converted into a large positive number.

The code for the function did have some security to it, by checking if the number specified in the function was larger than the allowed buffer size. However, since this if statement that checked for this was implemented using signed integers, it didn't revert to the maximum allowed buffer when specifying a negative number.

# Arithmetic and Over-/under-flow
When adding and multiplying numbers, the result can be greater than the assigned memory size. Fx. if adding negative numbers using Two's complement of size 4 bits, the result would give us a number of size 5 bits.
The same can happen for larger positive numbers written in plain binary.

When this happens, we use modular arithmetic. 

Example:

```
w=4, 8+11=19
  1000
+ 1011
------
10011  //19 mod 2^4 = 3
```

Simply put, we do the following:
$true\,value\:\:\: mod\:\:\: 2^w$

# Shifting
Shifting is basically moving the binary pattern

Say you have the binary number 1011001

And we shit this to the left by 3 we get the following:
1001000.
We simply "move" the binary numbers to the left. When a number exceeds the binary pattern it gets removed and 0's get added on the other side.

Shifting to the right is the same. However for right-shift there's also the Logical shift and the Arithmetic shift.

## Logical shift
By logical shift we do as for the left-shift, we simply fill with 0's at the left side of the binary number.

## Arithmetic Shift
With Arithmetic shift we repeat the most valued bit from the argument to the right

Below is an example of both Logical and Arithmetic shift for both left and right shift.
![[Pasted image 20230215094852.png]]