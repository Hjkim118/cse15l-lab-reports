```
{
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$
}
```
- It was working in /lecture1/messages directory before the command was written and after executing the code, it moved to /home directory.
- The cd command without arguments puts the user in the home directory so it moves me to /home from /lecture1/messages directory.
- This was not an error.

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
- It was working in /home directory before the command was written and after executing the code, it moved to /lecture1 directory.
- Since cd is the command used for changing the directory, it moved from home to /lecture1 directory.
- This was not an error.

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- Since cd is the command used for changing the directory, when it is used with files, it does not execute anything.
- This showed an error since the user put in the file as an argument of cd instead of a directory. So This showed an error sign that the file is not a directory.

```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
[user@sahara ~/lecture1]$
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- The ls command shows the list of files in the directory so it showed every 4 files in /lecture1 directory.
- This was not an error.

```
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  ko.txt  zh-cn.txt
[user@sahara ~/lecture1]$
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- This command, ls is used for showing list files in the directory, and this showed 4 files in this lecture1 directory(where it is right now).
- This was not an error.

```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- Command ls shows the files that are in the folder of files in the path so when used with files, it contains only one file itself and it shows itself as a result.
- This was not an error.

```
[user@sahara ~/lecture1]$ cat
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- The cat command lets you create, merge, or print files in the standard output screen or to another file. It did nothing and waited for the user to type in which file to execute.
- This was an error since the user had to put in which file for the command cat to be executed, but there were no arguments given after the command.

```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$ 
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- Since cat is for print, creating, or merging files, if it is used with a directory, it does not execute anything.
- This is an error because the command cat needs the file name as an argument instead of a directory.

```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}
```
- It was working in /lecture1 directory before the command was written and after executing the code, it stayed in /lecture1 directory.
- One of usage of the cat command is for printing files, so it printed out the code written in Hello.java.
- This is not an error.

