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

> **Note:** [ - Begins the CSI (Control Sequence Introducer)

## ESCAPE CHARACTER

The Escape character is represented by the ASCII value 27 or the hexadecimal value 0x1B. In most programming languages, you can represent it using an escape code like \x1B or \033.

An ANSI escape sequence typically starts with the Escape character, followed by an open square bracket [, a sequence of numeric codes separated by semicolons, and ends with the letter m. The numeric codes define the desired action, such as changing the text color or enabling bold text.

The \e escape sequence is another way to represent the "Escape" character in some programming languages and scripting environments, such as Ruby and Bash shell scripts. It is equivalent to the ASCII value 27 or the hexadecimal value 0x1B, which is the same as \x1B or \033.

For example, to change the text color to red, you would use the following escape sequence:

- Ctrl-Key: `^[`
- Octal: `\033`
- Unicode: `\u001b`
- Hexadecimal: `\x1B`
- Decimal: `27`

## Sequences

- `ESC` - sequence starting with `ESC` (`\x1B`)
- `CSI` - Control Sequence Introducer: sequence starting with `ESC [` or CSI (`\x9B`)
- `DCS` - Device Control String: sequence starting with `ESC P` or DCS (`\x90`)
- `OSC` - Operating System Command: sequence starting with `ESC ]` or OSC (`\x9D`)

Any whitespaces between sequences and arguments should be ignored. They are present for improved readability.

## General ASCII Codes

| Name  | decimal | octal | hex  | C-escape | Ctrl-Key | Description                    |
| ----- | ------- | ----- | ---- | -------- | -------- | ------------------------------ |
| `BEL` | 7       | 007   | 0x07 | `\a`     | `^G`     | Terminal bell                  |
| `BS`  | 8       | 010   | 0x08 | `\b`     | `^H`     | Backspace                      |
| `HT`  | 9       | 011   | 0x09 | `\t`     | `^I`     | Horizontal TAB                 |
| `LF`  | 10      | 012   | 0x0A | `\n`     | `^J`     | Linefeed (newline)             |
| `VT`  | 11      | 013   | 0x0B | `\v`     | `^K`     | Vertical TAB                   |
| `FF`  | 12      | 014   | 0x0C | `\f`     | `^L`     | Formfeed (also: New page `NP`) |
| `CR`  | 13      | 015   | 0x0D | `\r`     | `^M`     | Carriage return                |
| `ESC` | 27      | 033   | 0x1B | `\e`[*](#escape) | `^[` | Escape character           |
| `DEL` | 127     | 177   | 0x7F | `<none>` | `<none>` | Delete character               |

<div id="escape"></div>

> **Note:** Some control escape sequences, like `\e` for `ESC`, are not guaranteed to work in all languages and compilers. It is recommended to use the decimal, octal or hex representation as escape code.



> **Note:** The **Ctrl-Key** representation is simply associating the non-printable characters from ASCII code 1 with the printable (letter) characters from ASCII code 65 ("A"). ASCII code 1 would be `^A` (Ctrl-A), while ASCII code 7 (BEL) would be `^G` (Ctrl-G). This is a common representation (and input method) and historically comes from one of the VT series of terminals.

## Cursor Controls

| ESC Code Sequence                                  | Description                                              |
| :------------------------------------------------- | :------------------------------------------------------- |
| `ESC[H`                                            | moves cursor to home position (0, 0)                     |
| `ESC[{line};{column}H` <br> `ESC[{line};{column}f` | moves cursor to line #, column #                         |
| `ESC[#A`                                           | moves cursor up # lines                                  |
| `ESC[#B`                                           | moves cursor down # lines                                |
| `ESC[#C`                                           | moves cursor right # columns                             |
| `ESC[#D`                                           | moves cursor left # columns                              |
| `ESC[#E`                                           | moves cursor to beginning of next line, # lines down     |
| `ESC[#F`                                           | moves cursor to beginning of previous line, # lines up   |
| `ESC[#G`                                           | moves cursor to column #                                 |
| `ESC[6n`                                           | request cursor position (reports as `ESC[#;#R`)          |
| `ESC M`                                            | moves cursor one line up, scrolling if needed            |
| `ESC 7`                                            | save cursor position (DEC)                               |
| `ESC 8`                                            | restores the cursor to the last saved position (DEC)     |
| `ESC[s`                                            | save cursor position (SCO)                               |
| `ESC[u`                                            | restores the cursor to the last saved position (SCO)     |

> **Note:** Some sequences, like saving and restoring cursors, are private sequences and are not standardized. While some terminal emulators (i.e. xterm and derived) support both SCO and DEC sequences, they are likely to have different functionality. It is therefore recommended to use DEC sequences.

## Erase Functions

| ESC Code Sequence | Description                               |
| :---------------- | :---------------------------------------- |
| `ESC[J`           | erase in display (same as ESC\[0J)        |
| `ESC[0J`          | erase from cursor until end of screen     |
| `ESC[1J`          | erase from cursor to beginning of screen  |
| `ESC[2J`          | erase entire screen                       |
| `ESC[3J`          | erase saved lines                         |
| `ESC[K`           | erase in line (same as ESC\[0K)           |
| `ESC[0K`          | erase from cursor to end of line          |
| `ESC[1K`          | erase start of line to the cursor         |
| `ESC[2K`          | erase the entire line                     |

> Note: Erasing the line won't move the cursor, meaning that the cursor will stay at the last position it was at before the line was erased. You can use `\r` after erasing the line, to return the cursor to the start of the current line.

## Colors / Graphics Mode

| ESC Code Sequence | Reset Sequence | Description                                                |
| :---------------- | :------------- | :--------------------------------------------------------- |
| `ESC[1;34;{...}m` |                | Set graphics modes for cell, separated by semicolon (`;`). |
| `ESC[0m`          |                | reset all modes (styles and colors)                        |
| `ESC[1m`          | `ESC[22m`      | set bold mode.                                             |
| `ESC[2m`          | `ESC[22m`      | set dim/faint mode.                                        |
| `ESC[3m`          | `ESC[23m`      | set italic mode.                                           |
| `ESC[4m`          | `ESC[24m`      | set underline mode.                                        |
| `ESC[5m`          | `ESC[25m`      | set blinking mode                                          |
| `ESC[7m`          | `ESC[27m`      | set inverse/reverse mode                                   |
| `ESC[8m`          | `ESC[28m`      | set hidden/invisible mode                                  |
| `ESC[9m`          | `ESC[29m`      | set strikethrough mode.                                    |

> **Note:** Some terminals may not support some of the graphic mode sequences listed above.

> **Note:** Both dim and bold modes are reset with the `ESC[22m` sequence. The `ESC[21m` sequence is a non-specified sequence for double underline mode and only work in some terminals and is reset with `ESC[24m`.

### Color codes

Most terminals support 8 and 16 colors, as well as 256 (8-bit) colors. These colors are set by the user, but have commonly defined meanings.

#### 8-16 Colors

| Color Name | Foreground Color Code | Background Color Code |
| :--------- | :-------------------- | :-------------------- |
| Black      | `30`                  | `40`                  |
| Red        | `31`                  | `41`                  |
| Green      | `32`                  | `42`                  |
| Yellow     | `33`                  | `43`                  |
| Blue       | `34`                  | `44`                  |
| Magenta    | `35`                  | `45`                  |
| Cyan       | `36`                  | `46`                  |
| White      | `37`                  | `47`                  |
| Default    | `39`                  | `49`                  |
| Reset      | `0`                   | `0`                   |

> **Note:** the _Reset_ color is the reset code that resets _all_ colors and text effects, Use _Default_ color to reset colors only.

Most terminals, apart from the basic set of 8 colors, also support the "bright" or "bold" colors. These have their own set of codes, mirroring the normal colors, but with an additional `;1` in their codes:

```sh
# Set style to bold, red foreground.
\x1b[1;31mHello
# Set style to dimmed white foreground with red background.
\x1b[2;37;41mWorld
```

Terminals that support the [aixterm specification](https://sites.ualberta.ca/dept/chemeng/AIX-43/share/man/info/C/a_doc_lib/cmds/aixcmds1/aixterm.htm) provides bright versions of the ISO colors, without the need to use the bold modifier:

| Color Name     | Foreground Color Code | Background Color Code |
| :------------- | :-------------------- | :-------------------- |
| Bright Black   | `90`                  | `100`                 |
| Bright Red     | `91`                  | `101`                 |
| Bright Green   | `92`                  | `102`                 |
| Bright Yellow  | `93`                  | `103`                 |
| Bright Blue    | `94`                  | `104`                 |
| Bright Magenta | `95`                  | `105`                 |
| Bright Cyan    | `96`                  | `106`                 |
| Bright White   | `97`                  | `107`                 |

#### 256 Colors

The following escape codes tells the terminal to use the given color ID:

| ESC Code Sequence | Description           |
| :---------------- | :-------------------- |
| `ESC[38;5;{ID}m` | Set foreground color. |
| `ESC[48;5;{ID}m` | Set background color. |

Where `{ID}` should be replaced with the color index from 0 to 255 of the following color table:

![256 Color table][ansi_color_png]

The table starts with the original 16 colors (0-15).

The proceeding 216 colors (16-231) or formed by a 3bpc RGB value offset by 16, packed into a single value.

The final 24 colors (232-255) are grayscale starting from a shade slighly lighter than black, ranging up to shade slightly darker than white.

Some emulators interpret these steps as linear increments (`256 / 24`) on all three channels, although some emulators may explicitly define these values.

#### RGB Colors

More modern terminals supports [Truecolor](https://en.wikipedia.org/wiki/Color_depth#True_color_.2824-bit.29) (24-bit RGB), which allows you to set foreground and background colors using RGB.

These escape sequences are usually not well documented.

| ESC Code Sequence       | Description                  |
| :---------------------- | :--------------------------- |
| `ESC[38;2;{r};{g};{b}m` | Set foreground color as RGB. |
| `ESC[48;2;{r};{g};{b}m` | Set background color as RGB. |

> Note that `;38` and `;48` corresponds to the 16 color sequence and is interpreted by the terminal to set the foreground and background color respectively. Where as `;2` and `;5` sets the color format.

-----------
[//]: <> (ALL REFERENCES)
[ansi_ref]: https://ansi.org/
[ansi_color_png]: https://raw.githubusercontent.com/DipadityaDas/Bash-Setup/main/color-codes.png