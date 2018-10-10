## Introduction

Implementations for encryption algorithms including DES, RSA.

## Test
plaintext: 01234567
key: 12345678

### Encryption

```
Replacement 1 C               00000000 00000000 11111111 1111 
Replacement 1 D               01100110 01111000 10000000 1111 
1 leftShifting C              00000000 00000001 11111111 1110 
1 leftShifting D              11001100 11110001 00000001 1110 
1 concatChars                 00000000 00000001 11111111 11101100 11001111 00010000 00011110 
subKey[1]                     01010000 00101100 10101100 01010111 00101010 11000010 

2 leftShifting C              00000000 00000011 11111111 1100 
2 leftShifting D              10011001 11100010 00000011 1101 
2 concatChars                 00000000 00000011 11111111 11001001 10011110 00100000 00111101 
subKey[2]                     01010000 10101100 10100100 01010000 10100011 01000111 

3 leftShifting C              00000000 00001111 11111111 0000 
3 leftShifting D              01100111 10001000 00001111 0110 
3 concatChars                 00000000 00001111 11111111 00000110 01111000 10000000 11110110 
subKey[3]                     11010000 10101100 00100110 11110110 10000100 10001100 

4 leftShifting C              00000000 00111111 11111100 0000 
4 leftShifting D              10011110 00100000 00111101 1001 
4 concatChars                 00000000 00111111 11111100 00001001 11100010 00000011 11011001 
subKey[4]                     11100000 10100110 00100110 01001000 00110111 11001011 

5 leftShifting C              00000000 11111111 11110000 0000 
5 leftShifting D              01111000 10000000 11110110 0110 
5 concatChars                 00000000 11111111 11110000 00000111 10001000 00001111 01100110 
subKey[5]                     11100000 10010110 00100110 00111110 11110000 00101001 

6 leftShifting C              00000011 11111111 11000000 0000 
6 leftShifting D              11100010 00000011 11011001 1001 
6 concatChars                 00000011 11111111 11000000 00001110 00100000 00111101 10011001 
subKey[6]                     11100000 10010010 01110010 01100010 01011101 01100010 

7 leftShifting C              00001111 11111111 00000000 0000 
7 leftShifting D              10001000 00001111 01100110 0111 
7 concatChars                 00001111 11111111 00000000 00001000 10000000 11110110 01100111 
subKey[7]                     10100100 11010010 01110010 10001100 10101001 00111010 

8 leftShifting C              00111111 11111100 00000000 0000 
8 leftShifting D              00100000 00111101 10011001 1110 
8 concatChars                 00111111 11111100 00000000 00000010 00000011 11011001 10011110 
subKey[8]                     10100110 01010011 01010010 11100101 01011110 01010000 

9 leftShifting C              01111111 11111000 00000000 0000 
9 leftShifting D              01000000 01111011 00110011 1100 
9 concatChars                 01111111 11111000 00000000 00000100 00000111 10110011 00111100 
subKey[9]                     00100110 01010011 01010011 11001011 10011010 01000000 

10 leftShifting C             11111111 11100000 00000000 0001 
10 leftShifting D             00000001 11101100 11001111 0001 
10 concatChars                11111111 11100000 00000000 00010000 00011110 11001100 11110001 
subKey[10]                    00101111 01010001 01010001 11010000 11000111 00111100 

11 leftShifting C             11111111 10000000 00000000 0111 
11 leftShifting D             00000111 10110011 00111100 0100 
11 concatChars                11111111 10000000 00000000 01110000 01111011 00110011 11000100 
subKey[11]                    00001111 01000001 11011001 00011001 00011110 10001100 

12 leftShifting C             11111110 00000000 00000001 1111 
12 leftShifting D             00011110 11001100 11110001 0000 
12 concatChars                11111110 00000000 00000001 11110001 11101100 11001111 00010000 
subKey[12]                    00011111 01000001 10011001 11011000 01110000 10110001 

13 leftShifting C             11111000 00000000 00000111 1111 
13 leftShifting D             01111011 00110011 11000100 0000 
13 concatChars                11111000 00000000 00000111 11110111 10110011 00111100 01000000 
subKey[13]                    00011111 00001001 10001001 00100011 01101010 00101101 

14 leftShifting C             11100000 00000000 00011111 1111 
14 leftShifting D             11101100 11001111 00010000 0001 
14 concatChars                11100000 00000000 00011111 11111110 11001100 11110001 00000001 
subKey[14]                    00011011 00101000 10001101 10110010 00111001 10010010 

15 leftShifting C             10000000 00000000 01111111 1111 
15 leftShifting D             10110011 00111100 01000000 0111 
15 concatChars                10000000 00000000 01111111 11111011 00110011 11000100 00000111 
subKey[15]                    00011001 00101100 10001100 10100101 00000011 00110111 

16 leftShifting C             00000000 00000000 11111111 1111 
16 leftShifting D             01100110 01111000 10000000 1111 
16 concatChars                00000000 00000000 11111111 11110110 01100111 10001000 00001111 
subKey[16]                    01010001 00101100 10001100 10100111 01000011 11000000 

plaintext after ip            00000000 11111111 11110000 10101010 00000000 11111111 00000000 11001100 
L0                            00000000 11111111 11110000 10101010 
R0                            00000000 11111111 00000000 11001100 
N = 1
coreEncrypting
32-bit input                  00000000 11111111 00000000 11001100 
Selection                     00000000 00010111 11111110 10000000 00010110 01011000 
subKey                        01010000 00101100 10101100 01010111 00101010 11000010 
xor                           01010000 00111011 01010010 11010111 00111100 10011010 
SBox                          01101101 10000010 00001110 11110000 
P Replacement                 00010010 01111000 11000111 00011001 
left                          00000000 11111111 00000000 11001100 
right                         00010010 10000111 00110111 10110011 

N = 2
coreEncrypting
32-bit input                  00010010 10000111 00110111 10110011 
Selection                     10001010 01010100 00001110 10011010 11111101 10100110 
subKey                        01010000 10101100 10100100 01010000 10100011 01000111 
xor                           11011010 11111000 10101010 11001010 01011110 11100001 
SBox                          01110010 01101011 10010010 00100010 
P Replacement                 11100001 01100011 10000110 01000110 
left                          00010010 10000111 00110111 10110011 
right                         11100001 10011100 10000110 10001010 

N = 3
coreEncrypting
32-bit input                  11100001 10011100 10000110 10001010 
Selection                     01110000 00111100 11111001 01000000 11010100 01010101 
subKey                        11010000 10101100 00100110 11110110 10000100 10001100 
xor                           10100000 10010000 11011111 10110110 01010000 11011001 
SBox                          11011111 01111001 00100010 00000000 
P Replacement                 11000100 10101001 11000000 11010110 
left                          11100001 10011100 10000110 10001010 
right                         11010110 00101110 11110111 01100101 

N = 4
coreEncrypting
32-bit input                  11010110 00101110 11110111 01100101 
Selection                     11101010 11000001 01011101 01111010 11101011 00001011 
subKey                        11100000 10100110 00100110 01001000 00110111 11001011 
xor                           00001010 01100111 01111011 00110010 11011100 11000000 
SBox                          01001011 11110111 10111111 01011101 
P Replacement                 11111111 01111001 11111001 10101100 
left                          11010110 00101110 11110111 01100101 
right                         00011110 11100101 01111111 00100110 

N = 5
coreEncrypting
32-bit input                  00011110 11100101 01111111 00100110 
Selection                     00001111 11010111 00001010 10111111 11101001 00001100 
subKey                        11100000 10010110 00100110 00111110 11110000 00101001 
xor                           11101111 01000001 00101100 10000001 00011001 00100101 
SBox                          00001100 10010111 01000110 10111110 
P Replacement                 10001110 01101110 00010101 00111001 
left                          00011110 11100101 01111111 00100110 
right                         01011000 01000000 11100010 01011100 

N = 6
coreEncrypting
32-bit input                  01011000 01000000 11100010 01011100 
Selection                     00101111 00000010 00000001 01110000 01000010 11111000 
subKey                        11100000 10010010 01110010 01100010 01011101 01100010 
xor                           11001111 10010000 01110011 00010010 00011111 10011010 
SBox                          10110000 11010100 01000100 00100000 
P Replacement                 00000100 10000101 00010111 00001010 
left                          01011000 01000000 11100010 01011100 
right                         00011010 01100000 01101000 00101100 

N = 7
coreEncrypting
32-bit input                  00011010 01100000 01101000 00101100 
Selection                     00001111 01000011 00000000 00110101 00000001 01011000 
subKey                        10100100 11010010 01110010 10001100 10101001 00111010 
xor                           10101011 10010001 01110010 10111001 10101000 01100010 
SBox                          01100000 00000001 10000111 01101011 
P Replacement                 10001001 00110010 10101110 00001000 
left                          00011010 01100000 01101000 00101100 
right                         11010001 01110010 01001100 01010100 

N = 8
coreEncrypting
32-bit input                  11010001 01110010 01001100 01010100 
Selection                     01101010 00101011 10100100 00100101 10000010 10101001 
subKey                        10100110 01010011 01010010 11100101 01011110 01010000 
xor                           11001100 01111000 11110110 11000000 11011100 11111001 
SBox                          10110111 10101110 11111001 01010011 
P Replacement                 01110011 11010110 01111011 11010110 
left                          11010001 01110010 01001100 01010100 
right                         01101001 10110110 00010011 11111010 

N = 9
coreEncrypting
32-bit input                  01101001 10110110 00010011 11111010 
Selection                     00110101 00111101 10101100 00001010 01111111 11110100 
subKey                        00100110 01010011 01010011 11001011 10011010 01000000 
xor                           00010011 01101110 11111111 11000001 11100101 10110100 
SBox                          11010110 01011110 11111011 01111010 
P Replacement                 01111111 11110111 10110100 11010010 
left                          01101001 10110110 00010011 11111010 
right                         10101110 10000101 11111000 10000110 

N = 10
coreEncrypting
32-bit input                  10101110 10000101 11111000 10000110 
Selection                     01010101 11010100 00001011 11111111 00010100 00001101 
subKey                        00101111 01010001 01010001 11010000 11000111 00111100 
xor                           01111010 10000101 01011010 00101111 11010011 00110001 
SBox                          01111010 01011100 01111000 10001111 
P Replacement                 01111100 00001111 10011010 11100011 
left                          10101110 10000101 11111000 10000110 
right                         00010101 10111001 10001001 00011001 

N = 11
coreEncrypting
32-bit input                  00010101 10111001 10001001 00011001 
Selection                     10001010 10111101 11110011 11000101 00101000 11110010 
subKey                        00001111 01000001 11011001 00011001 00011110 10001100 
xor                           10000101 11111100 00101010 11011100 00110110 01111110 
SBox                          11110101 10111011 10011111 00101000 
P Replacement                 10111101 11100000 11100111 01011110 
left                          00010101 10111001 10001001 00011001 
right                         00010011 01100101 00011111 11011000 

N = 12
coreEncrypting
32-bit input                  00010011 01100101 00011111 11011000 
Selection                     00001010 01101011 00001010 10001111 11111110 11110000 
subKey                        00011111 01000001 10011001 11011000 01110000 10110001 
xor                           00010101 00101010 10010011 01010111 10001110 01000001 
SBox                          01110111 11110111 11110001 11100001 
P Replacement                 11100101 01010101 11111111 10010111 
left                          00010011 01100101 00011111 11011000 
right                         11110000 11101100 01110110 10001110 

N = 13
coreEncrypting
32-bit input                  11110000 11101100 01110110 10001110 
Selection                     01111010 00010111 01011000 00111010 11010100 01011101 
subKey                        00011111 00001001 10001001 00100011 01101010 00101101 
xor                           01100101 00011110 11010001 00011001 10111110 01110000 
SBox                          10011100 01010100 00011011 11100000 
P Replacement                 00110100 10111001 00110100 00010011 
left                          11110000 11101100 01110110 10001110 
right                         00100111 11011100 00101011 11001011 

N = 14
coreEncrypting
32-bit input                  00100111 11011100 00101011 11001011 
Selection                     10010000 11111110 11111000 00010101 01111110 01010110 
subKey                        00011011 00101000 10001101 10110010 00111001 10010010 
xor                           10001011 11010110 01110101 10100111 01000111 11000100 
SBox                          00011110 11000101 00010100 01101000 
P Replacement                 11101000 00011001 00010101 00011010 
left                          00100111 11011100 00101011 11001011 
right                         00011000 11110101 01100011 10010100 

N = 15
coreEncrypting
32-bit input                  00011000 11110101 01100011 10010100 
Selection                     00001111 00010111 10101010 10110000 01111100 10101000 
subKey                        00011001 00101100 10001100 10100101 00000011 00110111 
xor                           00010110 00111011 00100110 00010101 01111111 10011111 
SBox                          01111000 00110000 00101110 00100010 
P Replacement                 00010100 00101010 10000110 10001110 
left                          00011000 11110101 01100011 10010100 
right                         00110011 11110110 10101101 01000101 

N = 16
coreEncrypting
32-bit input                  00110011 11110110 10101101 01000101 
Selection                     10011010 01111111 10101101 01010101 10101010 00001010 
subKey                        01010001 00101100 10001100 10100111 01000011 11000000 
xor                           11001011 01010011 00100001 11110010 11101001 11001010 
SBox                          11000111 11110011 00000011 10001111 
P Replacement                 11001100 11100011 11101001 00110101 
left                          00110011 11110110 10101101 01000101 
right                         11010100 00010110 10001010 10100001 

plaintext                     00110000 00110001 00110010 00110011 00110100 00110101 00110110 00110111 
key                           00110001 00110010 00110011 00110100 00110101 00110110 00110111 00111000 
encrypted text bits           10001011 10110100 01111010 00001100 11110000 10101001 01100010 01101101 
encrypted text                ´zð©bm  

```