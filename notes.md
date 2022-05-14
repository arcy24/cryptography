# Base64

Base64 Encoding Logic
Base64 encoding breaks binary data into 6-bit segments of 3 full bytes and represents those as printable characters in ASCII standard. It does that in essentially two steps.

The first step is to break the binary string down into 6-bit blocks. Base64 only uses 6 bits (corresponding to 2^6 = 64 characters) to ensure encoded data is printable and humanly readable. None of the special characters available in ASCII are used.

The 64 characters (hence the name Base64) are 10 digits, 26 lowercase characters, 26 uppercase characters as well as the Plus sign (+) and the Forward Slash (/). There is also a 65th character known as a pad, which is the Equal sign (=). This character is used when the last segment of binary data doesn't contain a full 6 bits.


# Base64 Encoding Example

For example, take three ASCII numbers 155, 162, and 233. These three numbers constitute a binary stream of 100110111010001011101001. A binary file, like an image, contains a binary stream running for tens or hundreds of thousands of zeroes and ones.

A Base64 encoder starts by chunking the binary stream into groupings of six characters: 100110 111010 001011 101001. Each of these groupings translates into the numbers 38, 58, 11, and 41.

A six-character binary stream converts between binary (or base-2) to decimal (base-10) characters by squaring each value represented by a 1 in the binary sequence with its positional square. Starting from the right and moving left, and starting with zero, the values in the binary stream represent 2^0, then 2^1, then 2^2, then 2^3, then 2^4, then 2^5.

Here's another way to look at it. Starting from the left, each position is worth 1, 2, 4, 8, 16, and 32. If the binary number has a 1 in the slot, you add that value; if it has a 0 in the slot, you don't. The binary string 100110 converts to the decimal number 38: 0*2^01 + 1*2^1 + 1*2^2 + 0*2^3 + 0*2^4 + 1*2^5 = 0+2+4+0+0+32.

Base64 encoding takes this binary string and breaks it down into the 6-bit values 38, 58, 11 and 41.

Finally, these numbers are converted to ASCII characters using the Base64 encoding table. The 6-bit values of this example translate to the ASCII sequence m6Lp.

Using the Base64 conversion table:

* 38 is m
* 58 is 6
* 11 is L
* 41 is p

This two-step process is applied to the entire binary string that's encoded.

To ensure the encoded data can be properly printed and does not exceed any mail server's line length limit, newline characters are inserted to keep line lengths below 76 characters. The newline characters are encoded like all other data.

Reference:

https://www.lifewire.com/base64-encoding-overview-1166412

