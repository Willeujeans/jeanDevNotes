# Number Representations
# Binary
_Base 2 representation of numbers using 0 and 1._
## Binary to Decimal
 42 -> 0b101010

  1   0   1   0   1   0
  ^   ^   ^   ^   ^   ^
  |   |   |   |   |   |
  |   |   |   |   |  $0*2^0$
  |   |   |   |  $1*2^1$
  |   |   |  $0*2^2$
  |   |  $1*2^3$
  |  $0*2^4$
 $1*2^5$
## Padding 0s
You can pad a binary number with leading zeros and it wont effect the result
00000101010 = 42
## Bits
A bit is either a 0 or a 1
## Bytes
8 bits form a byte
## One's Compliment
Flip all the bits in the number
## Two's Compliment
Flip all the bits, then add binary representation of 1
This is used to split the binary representation into half
Leading 0 being positive
Leading 1 being negative

# Hexadecimal
_Base 16 number system that uses 0-9 & a-f._
41719 = 0xa2f7
a = 10, b = 1, c = 12, d = 13, e = 14, f = 15

 a   2   f   7
 ^   ^   ^   ^
 |   |   |   |
 |   |   |  $7*16^0$
 |   |  $15*16^1$
 |  $2*16^2$
$10*16^3$ 