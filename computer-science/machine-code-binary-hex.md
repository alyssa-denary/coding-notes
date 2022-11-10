## Machine Code
- computer programming language consisting of binary or hexadecimal instructions which a computer can respond to directly

### Binary Code
https://www.youtube.com/watch?v=USCBCmwMCDA
![[Screen Shot 2022-11-08 at 11.58.13 AM.png]]

#### Data carried over wires that are on or off:
![[Screen Shot 2022-11-08 at 12.01.06 PM.png]]

#### Data Storage
source: https://www.learnhowtoprogram.com/computer-science/bit-manipulation-and-hashing/bits-bytes-and-binary-numbers
- **Bit**: Each wire with 1 or 0
- **Nibble**: Group of 4 bits
- **Byte**: 8 bits
- **Kilobyte**: 1024 bits (approximately 1000 bytes)
- **Megabyte**: 1024 kilobytes (approximately one million bytes)
- **Gigabyte**: 1024 megabytes (approximately one billion bytes)
- **Terabyte**: 1024 gigabytes (approximately one trillion bytes)
  
#### All data can be represented using binary:
##### Often broken down into bytes:
-   **1 bit**: 2 permutations
-   **2 bit**: 4 permutations
-   **3 bit**: 8 permutations
-   **4 bit**: 16 permutations
-   **5 bit**: 32 permutations
-   **6 bit**: 64 permutations
-   **7 bit**: 128 permutations
-   **8 bit**: 256 permutations
A group of eight bits put together is known as a **byte**. A byte consists of 256 different combinations if you include the number 00000000 — all the binary numbers between 00000000 and 11111111.

##### Numbers ![[Screen Shot 2022-11-08 at 12.00.21 PM.png]]
##### Text
- There are 255 characters represented in the extended set of ASCII character codes.
![[Screen Shot 2022-11-08 at 12.01.50 PM.png]]
![[Screen Shot 2022-11-08 at 12.02.52 PM.png]]
##### Images: Represented in pixels & RGB values
- Each pixel represented by 3 bytes: each red, green, & blue value ranging from 0 to 255
  ![[Screen Shot 2022-11-08 at 12.03.21 PM.png]]
##### Sound
  ![[Screen Shot 2022-11-08 at 12.04.47 PM.png]]
![[Screen Shot 2022-11-08 at 12.05.40 PM.png]]
![[Screen Shot 2022-11-08 at 12.01.06 PM.png]]

### Hexadecimal System
source: https://www.sciencedirect.com/topics/engineering/hexadecimal
- Base 16 
- This system, therefore, has numerals 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, and 15.
- Two-digit decimal numbers 10, 11, 12, 13, 14, and 15 must be represented by a single numeral to exist in this numbering system.
- A, B, C, D, E, and F are used to represent these values in hexadecimal and are treated as valid numerals
- Rarely do we work with numbers greater than 4096 in hexadecimal.
##### Example conversion from Decimal to Hexadecimal:
For Decimal number 538:
  1. First place zeros in all columns that are known to be too big.![[Screen Shot 2022-11-10 at 9.14.12 AM.png]]
  2. 538 − (2 × 256) = 26![[Screen Shot 2022-11-10 at 9.21.39 AM.png]]
  3. 26 − (1 × 16) = 10![[Screen Shot 2022-11-10 at 9.22.31 AM.png]]
  4. 10 − (10 * 1) = 0. Recall, 10 decimal is represented by Ah hexadecimal. ![[Screen Shot 2022-11-10 at 9.23.00 AM.png]]
  5. The complete value is then 21 Ah

##### Example conversion from Binary to Hex:
1. Binary to hex conversion is simple–that is why hex is used. Each group of 4 bits is converted to the corresponding hex digit, starting with the least significant four, and padding with leading zeros if necessary:![[Screen Shot 2022-11-10 at 9.26.31 AM.png]]
Math: 8+1               8+4+2+1            2+1                    8+4+1
Dec:    9                       15                     3                         13
1. 