# Complement

Often used to represent signed integers in computers

> I personally prefer the introduction of the concept of [Baidu Encyclopedia](https://baike.baidu.com/item/%E8%A1%A5%E7%A0%81/6854613), which is similar to adjusting the clock time forward and backward
> "0000 0000" (0) goes forward to "0000 0001" (1) and goes backward to "1111 1111" (-1)

**The essence of complement is "binary mapping of modular operations"**

Mapping negative numbers to $2^n - | negative |$ (n is the number of bits),
the complement gives the binary the ability to:

- Symbolic bits naturally participate in the operation,
  addition and subtraction are unified into addition
- Make 0 and -0 the same to avoid logic confusion
- And of course gives one more negative number to represent

## Magic Usage

- LowBit: `x & (-x)`

  Gets the lowest bit 1 of x in binary and is used to support the build/query base operation in the [[Binary Indexed Tree]].