# Integer and Floating Point Arithmetic (IEEE 754)

#### 2's Complement
- All of the integer types are represented by binary numbers of varying bit widths. For example, the byte value for 42 in binary is 00101010, where each position represents a power of two, starting with 2 to the power of 0 at the rightmost bit. The next bit position to the left would be 2 to the power of 1, or 2, continuing toward the left with 2 to the power of 2, or 4, then 8, 16, 32, and so on. So 42 has 1 bits set at positions 1, 3, and 5 (counting from 0 at the right); thus, 42 is the sum of 2 to the power 1 + 2 to the power 3 + 2 to the power 5, which is 2 + 8 + 32.
- All of the integer types (except char) are signed integers. This means that they can represent negative values as well as positive ones. Java uses an encoding known as **two’s complement**, which means that negative numbers are represented by inverting (changing 1’s to 0’s and vice versa) all of the bits in a value, then adding 1 to the result. For example, –42 is represented by inverting all of the bits in 42, or 00101010, which yields 11010101, then adding 1, which results in 11010110, or –42. To decode a negative number, first invert all of the bits, then add 1. For example, –42, or 11010110 inverted, yields 00101001, or 41, so when you add 1 you get 42.
- The reason Java (and most other computer languages) uses two’s complement is easy to see when you consider the issue of *zero crossing*. Assuming a byte value, zero is represented by 00000000. In one’s complement, simply inverting all of the bits creates 11111111, which creates negative zero. The trouble is that negative zero is invalid in integer math. This problem is solved by using two’s complement to represent negative values. When using two’s complement, 1 is added to the complement, producing 100000000. This produces a 1 bit too far to the left to fit back into the byte value, resulting in the desired behavior, where –0 is the same as 0, and 11111111 is the encoding for –1. Although we used a byte value in the preceding example, the same basic principle applies to all of Java’s integer types.
- In **two’s complement**, the positive numbers are exactly the same as before for unsigned binary numbers. A negative number, however, is represented by a binary number, which when added to its corresponding positive equivalent results in zero.

#### References
- [Binary Negative Numbers](https://ryanstutorials.net/binary-tutorial/binary-negative-numbers.php)
- [Signed Binary Numbers](https://www.electronics-tutorials.ws/binary/signed-binary-numbers.html)
- Significand == Mantissa == Coefficient
- [The simple math behind decimal-binary conversion algorithms](https://indepth.dev/posts/1019/the-simple-math-behind-decimal-binary-conversion-algorithms)
- [Floating Point Visually Explained](https://fabiensanglard.net/floating_point_visually_explained/)
- [Float Exposed](https://float.exposed/0x40490fdb)
- [What Every Programmer Should Know About Floating-Point Arithmetic](https://floating-point-gui.de/)
    + [Floating Point Arithmetic](https://floating-point-gui.de/formats/fp/)
- [Floating Point Numbers](https://www.doc.ic.ac.uk/~eedwards/compsys/float/)