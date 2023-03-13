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
  
In this example, rm is able to remove a directory because of the -r option. It then recursively deletes the contents of folders and subfolders in the specified directory.   
  
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
  
In this example, the -f option stops rm from needing to prompt the user to confirm the deletion. It simply removes the file without any prompting.    
  
Example 2:   
```

```
  
In this example, .    

This option is useful because it allows you to quickly delete files without needing to confirm each deletion if the file is protected. You can also pair this option with -r to completely remove folders in a single execution of the command.    
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html  

## Option 3: -i  
  
This option makes rm ask the user for confirmation with every file that is removed.   
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:list-examples-grader:508$ rm -i Server.class TestListExamples.class
rm: remove regular file 'Server.class'? yes
rm: remove regular file 'TestListExamples.class'? yes
```
  
In this example, the -i option forces rm to prompt the user for confirmation when deleting each file. Without the option, rm would automatically delete the files without prompting as long as the file was not protected.    
  
Example 2:   
```

```
  
In this exampe, .   
  
This option is useful if you want to make sure you aren't deleting important files. It allows you to double check the files you are deleting one by one to account for any mistakes you may make.    
  
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

This option can be useful when trying to specify directories for rm to delete without wanting to use -r. It could also help detect and refrain from removing folders that are not empty. This option may also help you clear out your workspace by allowing you to remove empty folders from command line.     
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html  
