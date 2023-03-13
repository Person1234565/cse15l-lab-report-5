# Revisiting Lab Report 3: Options for command rm 
## Option 1: -r  
  
This option allows rm to remove directories and the contents inside of them recursively.  
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:~:501$ ls
lab7  list-examples-grader  perl5
[cs15lwi23ama@ieng6-201]:~:502$ rm -r lab7/
rm: remove write-protected regular file 'lab7/.git/objects/pack/pack-95bb68967ffc702a53699fc5b1f06862a64ec40e.pack'? yes
rm: remove write-protected regular file 'lab7/.git/objects/pack/pack-95bb68967ffc702a53699fc5b1f06862a64ec40e.idx'? yes
rm: remove write-protected regular file 'lab7/.git/objects/40/9fe006b3ca9186ec5491f3969c515d792017b0'? yes
[cs15lwi23ama@ieng6-201]:~:503$ ls
list-examples-grader  perl5
```  
  
In this example, .   
  
Example 2:  
```

```  
  
In this example, . 

This option is extremely useful because it allows you to delete full directories very quickly from command line. Rather than specifying individual files, you can simply specify the folder those files are in to delete all of them.   
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html     
  
## Option 2: -f  
  
This option makes rm not ask the user for confirmation for every file being removed and ignores files that don't exist.    
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:list-examples-grader:505$ ls
ExecExamples.class  ListExamples.class       TestListExamples.class
ExecHelpers.class   ListExamples.java        TestListExamples.java
GradeServer.class   Server.class             URLHandler.class
GradeServer.java    Server.java              grade.sh
Handler.class       ServerHttpHandler.class  lib
IsMoon.class        StringChecker.class      student-submission
[cs15lwi23ama@ieng6-201]:list-examples-grader:506$ rm -f URLHandler.class
[cs15lwi23ama@ieng6-201]:list-examples-grader:507$ ls
ExecExamples.class  ListExamples.class       TestListExamples.class
ExecHelpers.class   ListExamples.java        TestListExamples.java
GradeServer.class   Server.class             grade.sh
GradeServer.java    Server.java              lib
Handler.class       ServerHttpHandler.class  student-submission
IsMoon.class        StringChecker.class
```
  
In this example, .   
  
Example 2:   
```

```
  
In this example, .    

This option can be useful .    
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html  

## Option 3: -i  
  
This option makes rm ask the user for confirmation with every file that is removed.   
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:list-examples-grader:508$ rm -i Server.class TestListExamples.class
rm: remove regular file 'Server.class'? yes
rm: remove regular file 'TestListExamples.class'? yes
```
  
In this example, .   
  
Example 2:   
```

```
  
In this exampe, .   
  
This option is extremely useful .   
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html    
  
## Option 4: -d  
  
This option allows rm delete directories that are empty.   
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:~:512$ ls
empty  list-examples-grader  perl5
[cs15lwi23ama@ieng6-201]:~:513$ ls empty/
[cs15lwi23ama@ieng6-201]:~:514$ rm empty/
rm: cannot remove 'empty/': Is a directory
[cs15lwi23ama@ieng6-201]:~:515$ rm -d empty/
[cs15lwi23ama@ieng6-201]:~:516$ ls
list-examples-grader  perl5

```
  
In this example, the rm command .   
  
Example 2:   
```


```

In this example, the rm command. 

This option can be useful when trying to .    
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html  
