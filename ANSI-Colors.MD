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



-----------
[//]: <> (ALL REFERENCES)
[ansi_ref]: https://ansi.org/