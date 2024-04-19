# echo $$

`$$` is a special variable in the shell that represents the PID of the current shell instance.

When you run `echo $$`, it prints the PID of the shell in which you are working. This can be particularly useful for scripting purposes, such as identifying the running process of the script itself or for logging and monitoring activities based on the shell's PID. It can also help in managing processes, for instance, if you need to kill the shell or track its activities through other commands.
