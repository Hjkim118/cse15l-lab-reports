```
ssh cs15lfa23ar@ieng6.ucsd.edu 
```
`<enter>`

![Image](lab4_1.png)

This command made me access to remote computer

```
git clone https://github.com/Hjkim118/lab7 
```
`<enter>`

![Image](lab4_2.png)

This command made me able to clone https://github.com/Hjkim118/lab7 into remote computer

```
cd lab7
```
`<enter>`

![Image](lab4_3.png)

This command changed my directory to lab7 in remote computer directories

```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
`<enter>`

![Image](lab4_4.png)

These commmands were for testing with ListExamplesTests.java file if the ListExamples.java had no errors.

```
vim ListExamples.java
```
`<enter>`

This command was for accessing ListExamples.java file to see the code and edit if there are wrong lines.

Keys pressed:

`<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` `<down>` 
`<right>` `<right>` `<right>` `<right>` `<right>` `<right>` `<right>` `<right>` `<right>` `<right>` `<right>` 
`x` `i` `2` `<esc>` `:wq!` 
`<enter>`

Pressed `<down>` 43 times to go down until the line that had an error and `<right>` to go right to sepcify the place I want to fix. Pressed `x` to delete 1, and pressed `i` and `2` to insert 2 in that place.
Then I pressed `<esc>` to finish editing and pressed `:wq!` to exit with saved changes.

Keys Pressed:

`<up>` `<up>` `<up>` `<enter>`
`<up>` `<up>` `<up>` `<enter>` 

![Image](lab4_5.png)

Pressed `<up>` 3 times to find history of code which I typed 
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```

Pressed `<up>` 3 times again to find 
```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```

```
git add ListExamples.java
git commit -m "Add ListExamples.java"
```

![Image](lab4_6.png)
![Image](lab4_ll.png)

Added changed ListExamples.java to git.
