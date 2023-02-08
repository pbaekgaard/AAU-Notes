2. Problem 2.1 (p. 73)
A. 0010 0101 1011 1001 1101 0010
B. 1010 1110 0100 1001 -> 0xAE49
C. 1010 1000 1011 0011 1101
D. 11 0010 0010 1101 1001 0110 -> 0x322D96

3. Problem 2.3 (p. 74)

| Decimal | Binary    | Hexadecimal |
| ------- | --------- | ----------- |
| 0       | 0000 0000 | 0x00        |
| 158     | 1001 1110 | 0x9E        |
| 76      | 0100 1100 | 0x4C        |
| 145     | 1001 0001 | 0x91        |
| 174     | 1010 1110 | 0xAC        |
| 58      | 0011 1100 | 0x3A        |
| 241     | 1111 0001 | 0xF1        |
| 117     | 0111 0101 | 0x75        |
| 189     | 1011 1101 | 0xBD        |
| 245     | 1111 0101 | 0xF5        |

4. Problem 2.7 (p.85)
You simply convert each letter into its Hex value

| Letter | Hex |
| ------ | --- |
| m      | 6D  |
| n      | 6E  |
| o      | 6F  |
| p      | 70  |
| q      | 71  |
| r      | 72  | 


5. Problem 2.10 (p.90)

| Step      | \*x                         | \*y |
| --------- | --------------------------- | --- |
| Initially | a                           | b   |
| Step 1    | a                           | a^b |
| Step 2    | a^(a^b) = (a^a)^b = 0^b = b | a^b |
| Step 3    | b                           | b^(a^b) = (b^b)^a = 0^a = a    |


6. Problem 2.12 (p.91)

> [!NOTE] x reference
> x = 0x87654321
> w = 32

A. Using the AND operator (&) we can specify how many bytes we want from the hex string: x & 0xFF. Meaning we take the last 2 bytes from x.

B. Using the XOR operator (^) together with the NOT operator (~) and using a Hexadecimal of 0xFF, we can set 0's at the last two hex values of x

x ^ ~0xFF

C. Using the OR operator (|) we can specify the last two bytes with 0xFF.

x | 0xFF


7. Problem 2.14 (p.93)
To do the exercise, convert the hex into binary and perform the operations.  
As for the local expressions from the right side, you think of any **non 0 as true** and **0's as false**

| Expression     | Value | Expression       | Value |
| -------------- | ----- | ---------------- | ----- |
| 0x55 & 0x46    | 0x44  | 0x55 && 0x46     | 0x01  |
| 0x55 \| 0x46   | 0x57  | 0x55 \|\| 0x46   | 0x01  |
| ~0x55 \| ~0x46 | 0xBB  | !0x55 \|\| !0x46 | 0x00  |
| 0x55 & !0x46   | 0x00  | 0x55 && ~0x46    | 0x01  |
