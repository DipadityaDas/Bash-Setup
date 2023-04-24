# ANSI Colors

## What is ANSI ?

[__ANSI__][ansi_ref] stands for the [__American National Standards Institute__][ansi_ref]. It is a private, non-profit organization that oversees the development of voluntary consensus standards for products, services, processes, systems, and personnel in the United States. Founded in 1918, ANSI serves as a coordinator and facilitator for standardization efforts, working with various industries, government agencies, and consumer groups.

ANSI's __primary role__ is to:

1. Accredit standards developers and facilitate the development of American National Standards (ANS).
2. Represent the United States in international standardization efforts, such as those led by the International Organization for Standardization (ISO) and the International Electrotechnical Commission (IEC).
3. Approve national standards and ensure their consistency with international standards when possible.
4. Promote the use of American National Standards by both the public and private sectors.

## What is ANSI Color ?

ANSI colors refer to a set of color codes used in text-based terminals and terminal emulators to represent text in various colors and styles, such as bold, italic, underlined, or blinking. These color codes are based on the ANSI escape codes, which are a standardized set of sequences used to control text formatting and other output options on text terminals.

ANSI colors, in their basic form, are represented using 3 bits. The reason for this is that there are 8 basic ANSI colors, and 3 bits can represent 2^3 = 8 different values. Each bit corresponds to one of the primary color components: red, green, and blue. The presence of a bit (1) means that the color component is active, while its absence (0) means it is inactive.

Here's a breakdown of how the 3-bit ANSI colors are represented:

| Color   | bits | Representation |
| ------- | ---- | -------------- |
| Black   | 000 | no red, no green, no blue |
| Blue    | 001 | no red, no green,    blue |
| Green   | 010 | no red,    green, no blue |
| Cyan    | 011 | no red,    green,    blue |
| Red     | 100 |    red, no green, no blue |
| Magenta | 101 |    red, no green,    blue |
| Yellow  | 110 |    red,    green, no blue |
| White   | 111 |    red,    green,    blue |

However, it is essential to note that this 3-bit representation is only for the basic ANSI colors. As mentioned previously, some terminals and terminal emulators support extended color sets, like 16, 88, or 256 colors. In these cases, more bits are required to represent the additional colors. For instance, a 256-color palette would require 8 bits to represent each color (2^8 = 256).

## 8-bit ANSI Colors

8-bit ANSI colors refer to a color encoding scheme used in text-based interfaces and terminals, such as command-line environments. ANSI colors are based on the ANSI escape codes, which are sequences of characters that can be used to control the formatting, color, and other output options on text terminals.

The 8-bit color scheme supports a total of 256 colors, which are divided into different categories:

1. 16 basic colors (8 standard colors and their 8 bright variants):
	- 0-7: Standard colors (black, red, green, yellow, blue, magenta, cyan, and white)
	- 8-15: Bright versions of the standard colors

2. 216 colors (6x6x6 color cube):
	- 16-231: A 6x6x6 color cube, with each dimension representing the red, green, and blue color components. Each component can take on one of 6 values, ranging from 0 to 5.

3. 24 shades of gray:
	- 232-255: A series of grays, excluding pure black and pure white.

To use these colors in a terminal, you need to employ ANSI escape codes. These codes start with the ESC character (ASCII 27) followed by the [ character, then a number or sequence of numbers separated by semicolons, and finally, the letter m. For example, to set the foreground color to red, you would use the following escape code:

```bash
ESC[31m
```

Here, 31 is the ANSI code for red. To reset the terminal color to its default, you can use the code:

```bash
ESC[0m
```

In the context of ANSI escape sequences, "ESC" stands for the "Escape" character. It is a control character used to initiate an escape sequence, which allows you to modify the appearance or behavior of a text terminal, such as changing text color, background color, or text formatting (e.g., bold or underlined).

## ESCAPE CHARACTER

The Escape character is represented by the ASCII value 27 or the hexadecimal value 0x1B. In most programming languages, you can represent it using an escape code like \x1B or \033.

An ANSI escape sequence typically starts with the Escape character, followed by an open square bracket [, a sequence of numeric codes separated by semicolons, and ends with the letter m. The numeric codes define the desired action, such as changing the text color or enabling bold text.

The \e escape sequence is another way to represent the "Escape" character in some programming languages and scripting environments, such as Ruby and Bash shell scripts. It is equivalent to the ASCII value 27 or the hexadecimal value 0x1B, which is the same as \x1B or \033.

For example, to change the text color to red, you would use the following escape sequence:

| Octal   | Hexadecimal | Bash |
| -------- | -------- | ------ |
| \033[31m | \x1B[31m | \e[31m |
| \033[0m  | \x1B[0m  | \e[0m  |



-----------
[//]: <> (ALL REFERENCES)
[ansi_ref]: https://ansi.org/