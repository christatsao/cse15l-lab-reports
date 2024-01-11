# Lab 1 Summary
## Christa Tsao
## Thursday, Jan 11, 2024

Today, the basic filesystem commands we covered are `cd`, `ls`, and `cat`. 
Below are illustrated examples of using each commands with no arguments:
#1) No arguments
##`cd`

`[user@sahara ~]$ cd`

- This command when used with no arguments takes you back to the root directory. The above command was executed in the root directory already, but below is an example that is executed inside `~/lecture1/messages`. This is not an error.
  
```
[user@sahara ~]$ cd lecture1/messages/
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ pwd
/home
```

##`ls`

```
[user@sahara ~]$ cd
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```

- `ls` when given no arguments lists the files and directories in the current directory. In the above example, `ls` used in the root directory lists the `lecture1` directory. Following that example, I change directory into `lecture1`, and display the files and directories there. This is not an error. It follows that the expected output of `ls` matches the output given in the above example.

##`cat`

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

Moving on, below are illustrated examples of using each commands with a path to a directory.
#Passing directories as arguments)

#`cd`

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ cd messages
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ cd lecture1/messages/
[user@sahara ~/lecture1/messages]$
```

- Using `cd` with paths to directories changes the working directory to the specified directory. As you can see, the working directory at the beginning of the code is the root, and I then changed into lecture1, and then also showed an example of changing into messages from lecture1 and so on. This output is expected and is not an error. This happens because `cd` is a command that is supposed to navigate between directories.

#`ls`

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/messages/
en-us.txt  es-mx.txt  ru.txt  zh-cn.txt
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls messages
ls: cannot access 'messages': No such file or directory
```

- Using `ls` with a path to a directory prints the files in the referenced directory. This is not an error. This will throw an error, however, if you are referencing a directory that doesn't exist. For example, I tried to reference `/messages` while in the root directory, and it threw the error saying that it didn't exist. This happened because `ls` prints the files of the referenced directory, so the above output is expected.

#`cat`
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1/
cat: lecture1/: Is a directory
[user@sahara ~]$ cat lecture1/messages/
cat: lecture1/messages/: Is a directory
[user@sahara ~]$
```

- Using `cat` with a path to a directory just prints `cat: ` [insert the path given] `: Is a directory`. This is not an error, and it is expected output because cat prints the file contents, so cat will print that what you're giving it is a directory and not a file it can print. The working directory in the example is the root directory.

Lastly, below are illustrated examples of using each command with a path to a file as an argument.
#Passing a path to a file as an argument)


#`cd`

```
[user@sahara ~]$ cd lecture1/messages/
[user@sahara ~/lecture1/messages]$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
```

- Using `cd` with paths to files just prints that it is not a directory. This output is expected and is not an error. This happens because `cd` is a command that is supposed to navigate between directories. The working directory in the above example is `~lecture1/messages`.

#`ls`

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/messages/
[user@sahara ~/lecture1/messages]$ ls en-us.txt 
en-us.txt
[user@sahara ~/lecture1/messages]$ ls es-mx.txt 
es-mx.txt
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$ 
```

- Using `ls` with a path to a file prints the file's name. This is not an error. This happened because `ls` prints the files of the referenced directory, and since you are giving it just a path to a file, it will just print the name of the file. The working directory in this case was the root directory, and was then the lecture1 directory.

#`cat`

```
[user@sahara ~/lecture1]$ cat Hello.class
����A2

java/lang/Object<init>()java/lang/String




java/nio/file/Pathof;(Ljava/lang/String;[Ljava/lang/String;)Ljava/nio/file/Path;
!java/nio/charset/Standard
CharsetsUTF_8Ljava/nio/charset/Charset;

java/nio/file/Files
readStringB(Ljava/nio/file/Path;Ljava/nio/charset/Charset;)Ljava/lang/String;
 java/lang/SystemoutLjava/io/Print
Stream;
"#$
%&java/io/PrintStreamprintln(Ljava/lang/String;)V(HelloCodeLineNumberTablemain([Ljava/lang/String;)V
Exceptions/java/io/IOException
SourceFile
Hello.java!')*��*+,)9*2����L�
-.01[user@sahara ~/lecture1]$ cd messages/
[user@sahara ~/lecture1/messages]$ cat ru.txt
Привет, мир!
[user@sahara ~/lecture1/messages]$ 
```

- Using `cat` with a path to a file will print the content inside the referenced file. This is not an error and this is the intended use of the command. The working directory was the lecture1 folder and then it was the messages folder. You can also print multiple files at once, as illustrated below.

```
[user@sahara ~/lecture1/messages]$ cat ru.txt
Привет, мир!
[user@sahara ~/lecture1/messages]$ cat ru.txt en-us.txt es-mx.txt zh-cn.txt 
Привет, мир!
Hello World!
¡Hola Mundo!
你好世界
```
