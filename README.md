# Bash-Setup

```shell
echo 'PS1="\[\033[38;5;46m\][\u@\h \W]\[\033[38;5;46m\]\\$\[\033[m\] "' > /etc/profile.d/custom-prompt.sh
```

The /etc/profile.d directory is used to store system-wide shell scripts that get executed during
the initialization process of login and non-login shells. These scripts are usually used to set
up environment variables, modify the system's PATH, or configure other shell-related settings for
all users on the system.

When a user logs in, the /etc/profile file is sourced by the shell, which in turn sources all the
shell scripts (ending with .sh for Bourne shell compatible scripts like bash and ash or .csh for
C shell compatible scripts) present in the /etc/profile.d directory.

These scripts are executed in alphabetical order, and they can be used to set up the environment
without modifying the main /etc/profile file directly.