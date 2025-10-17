# base_conversion
A C program that converts numbers between any two bases (2 to 94) using printable ASCII characters as valid digits.
This program extends beyond the limits of binary, octal, decimal, and hexadecimal — allowing conversion across the entire printable ASCII range, including symbols.

🧠 Overview

Every number system uses a set of symbols (digits) to represent values.
In base 10, we use 0-9; in base 16, we use 0-9 and A-F.
But what if we want to go beyond that?

This program generalizes the concept by assigning every printable ASCII character (digits, uppercase and lowercase letters, and symbols) a numeric value — allowing you to perform base conversions up to base 94.

🚀 Features

✅ Convert between any two bases (2–94)
✅ Supports letters, numbers, and special characters as digits
✅ Displays the full set of symbols used for both input and output bases
✅ Handles invalid digits, base limits, and error checking gracefully
✅ Uses clean modular functions for digit-value mapping, conversions, and output

⚙️ How It Works
1. Digit Mapping

Each printable ASCII character is assigned a numeric value:

'0'–'9' → 0–9

'A'–'Z' → 10–35

'a'–'z' → 36–61

Symbols (! " # $ ... ~) → 62–93

This allows the program to use all 94 printable characters as unique digits.

2. Conversion Logic

The process occurs in two stages:

➤ Stage 1: Convert input number to base 10

Each digit is multiplied by its positional value and summed to get its base-10 equivalent.

long long to_base_10(char number_str[], int base);

➤ Stage 2: Convert base 10 to desired output base

The base-10 number is repeatedly divided by the target base, and remainders are converted back to characters.

void from_base_10(long long base_10_value, int base, char result_str[]);

🧩 Usage
Compilation
gcc base-convert.c -o base-convert

Execution
./base-convert -i <input_base> -o <output_base> <number>

💡 Examples
Example 1

Convert from base 16 (hexadecimal) to base 2 (binary):

./base-convert -i 16 -o 2 1A3


Output:

Input base: 16
Input digits: 0 1 2 ... F
Input number: 1A3
Output base: 2
Output digits: 0 1
Output number: 110100011

Example 2

Convert from base 62 (alphanumeric) to base 10:

./base-convert -i 62 -o 10 Zz


Output:

Input base: 62
Input digits: 0 1 2 ... z
Input number: Zz
Output base: 10
Output digits: 0 1 2 ... 9
Output number: 3843

Example 3

Convert using special symbols (base 80 to base 36):

./base-convert -i 80 -o 36 @#$

🧱 Internal Structure
Function	Purpose
value_of_digit()	Maps a character to its numeric value
char_for_value()	Maps a numeric value back to its character symbol
to_base_10()	Converts number from any base to base 10
from_base_10()	Converts base 10 number to any base
print_digits_for_base()	Displays the valid symbols for a given base
main()	Handles user input, validates arguments, and runs conversions
⚠️ Error Handling

The program actively checks for:

Invalid characters in the input number

Digits not allowed in the given base

Bases outside the supported range (2–94)

Incorrect usage format

If an error occurs, a clear message is displayed and the program exits safely.

🧮 Example of Supported Bases
Base	Symbols Used
2	0 1
10	0–9
16	0–9, A–F
36	0–9, A–Z
62	0–9, A–Z, a–z
94	All printable ASCII characters
🧑‍💻 Author

Palak Rajput
A computer science student exploring how logic, data representation, and creative design come together through code.
