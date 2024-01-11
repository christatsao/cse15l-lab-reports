# Lab 1 Summary
## Christa Tsao
## Thursday, Jan 11, 2024

Today, the basic filesystem commands we covered are `cd`, `ls`, and `cat`. 
Below are illustrated examples of using each commands with no arguments:

#`cd`

`[user@sahara ~]$ cd`

- This command when used with no arguments takes you back to the root directory. The above command was executed in the root directory already, but below is an example that is executed inside `~/lecture1/messages`. This is not an error.
  
```
[user@sahara ~]$ cd lecture1/messages/
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ pwd
/home
```

#`ls`

```
[user@sahara ~]$ cd
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```

- `ls` when given no arguments lists the files and directories in the current directory. In the above example, `ls` used in the root directory lists the `lecture1` directory. Following that example, I change directory into `lecture1`, and display the files and directories there. This is not an error. It follows that the expected output of `ls` matches the output given in the above example.

#`cat`

```
[user@sahara ~/lecture1]$ cat
```

- `cat` given no arguments does not return anything and the code hangs. The above example was executed in `~/lecture1`, but the command `cat` given no arguments hangs regardless of the working directory based on my observations. My guess for why `cat` hangs with no arguments is that it is waiting for an input that never arrives. What `cat` is supposed to do is print the contents of the referenced file. I tried to give input while it was running, and it just printed the string I gave it instead of executing the command. I believe this is considered an error.

```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ cat
^C
[user@sahara ~]$
```

```
[user@sahara ~]$ cd lecture1/messages
[user@sahara ~/lecture1/messages]$ cat en-us.txt
Hello World!
[user@sahara ~/lecture1/messages]$ cat
en-us.txt
en-us.txt
^C
```




