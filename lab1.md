```
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$
```
It was working in /lecture1/messages directory before the command was written and after executing the code, it moved to /home directory.
The cd command puts the user in home directory so it move me to /home from /lecture1/messages directory.

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
It was working in /home directory before the command was written and after executing the code, it moved to /lecture1 directory.

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$
```
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.

```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
[user@sahara ~/lecture1]$
```
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.
The ls command shows the list files of the directory so it showed every file in lecture1 directory.

```
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  ko.txt  zh-cn.txt
[user@sahara ~/lecture1]$
```
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.

```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$
```
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.

```
[user@sahara ~/lecture1]$ cat
```
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.
The cat command let you create, merge or print files in the standard output screen or to another file. It did nothing and waited for user to type in which file to execute.

```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$
```
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.

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
It was working in /lecture1 directory before the command was written and after executing the code, it it stayed in /lecture1 directory.

