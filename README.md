# Bash-Setup

```shell
echo 'PS1="\[\033[38;5;46m\][\u@\h \W]\[\033[38;5;46m\]\\$\[\033[m\] "' > /etc/profile.d/custom-prompt.sh

exec bash
```

1. echo: The echo command is used to print text to the console or file. In this case, it's used to print the value of the PS1 environment variable with the desired formatting.

2. PS1: The PS1 environment variable is used to define the primary shell prompt string. This string is displayed each time the shell prompts the user for input.

3. \[\033[38;5;46m\]: This is an ANSI escape sequence that sets the text color to a specific color from the 256-color palette (in this case, color 46). The sequence is composed of:

	- `\033`: This is the escape character.
	- `[`: This begins the CSI (Control Sequence Introducer).
	- `38;5`: This indicates that the following number is a 256-color index.
	- `46`: This is the color index (46)
	- `m`: This indicates the end of the sequence.

The /etc/profile.d directory is used to store system-wide shell scripts that get executed during
the initialization process of login and non-login shells. These scripts are usually used to set
up environment variables, modify the system's PATH, or configure other shell-related settings for
all users on the system.

When a user logs in, the /etc/profile file is sourced by the shell, which in turn sources all the
shell scripts (ending with .sh for Bourne shell compatible scripts like bash and ash or .csh for
C shell compatible scripts) present in the /etc/profile.d directory.

These scripts are executed in alphabetical order, and they can be used to set up the environment
without modifying the main /etc/profile file directly.