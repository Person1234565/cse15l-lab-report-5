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
[cs15lwi23ama@ieng6-201]:~:523$ ls listEx/list-examples-grader/
ExecExamples.class  IsMoon.class             StringChecker.class
ExecHelpers.class   ListExamples.class       TestListExamples.java
GradeServer.class   ListExamples.java        grade.sh
GradeServer.java    Server.java              lib
Handler.class       ServerHttpHandler.class  student-submission
[cs15lwi23ama@ieng6-201]:~:524$ rm -r listEx
rm: remove write-protected regular file 'listEx/list-examples-grader/.git/objects/pack/pack-a08b3635006da802fbace0d8f01d2e3421712eb8.pack'? yes
rm: remove write-protected regular file 'listEx/list-examples-grader/.git/objects/pack/pack-a08b3635006da802fbace0d8f01d2e3421712eb8.idx'? yes
rm: remove write-protected regular file 'listEx/list-examples-grader/student-submission/.git/objects/pack/pack-f998c88e799716c06b3f6af2e6c38122caecd9f4.pack'? yes
rm: remove write-protected regular file 'listEx/list-examples-grader/student-submission/.git/objects/pack/pack-f998c88e799716c06b3f6af2e6c38122caecd9f4.idx'? yes
[cs15lwi23ama@ieng6-201]:~:525$ ls listEx
ls: cannot access listEx: No such file or directory
```  
  
In this example, rm is again able to delete a directory due to the -r command. It is also able to delete the subfolders inside of the specified directory as the command removes recursively. 

This option is extremely useful because it allows you to delete full directories very quickly from command line. Rather than specifying individual files, you can simply specify the folder those files are in to delete all of them.   
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html     
  
## Option 2: -f  
  
This option makes rm not ask the user for confirmation for every file being removed and ignores files that don't exist.    
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:~:576$ ls
goodbye.txt  hello.txt  list-examples-grader  perl5
[cs15lwi23ama@ieng6-201]:~:577$ rm -f hello hello.txt goodbye.txt
[cs15lwi23ama@ieng6-201]:~:578$ ls
list-examples-grader  perl5
```
  
In this example, the -f option stops rm from outputting an error message that hello does not exist. It simply removes the existing files without any error messages.    
  
Example 2:   
```
[cs15lwi23ama@ieng6-201]:pack:532$ rm pack-a08b3635006da802fbace0d8f01d2e3421712eb8.pack
rm: remove write-protected regular file 'pack-a08b3635006da802fbace0d8f01d2e3421712eb8.pack'? no
[cs15lwi23ama@ieng6-201]:pack:533$ rm -f pack-a08b3635006da802fbace0d8f01d2e3421712eb8.pack
[cs15lwi23ama@ieng6-201]:pack:534$ cat pack-a08b3635006da802fbace0d8f01d2e3421712eb8.pack
cat: pack-a08b3635006da802fbace0d8f01d2e3421712eb8.pack: No such file or directory
```
  
In this example, the specified file is a protected file, which causes rm to prompt confirmation on whether to remove it or not. By including the -f option, the rm command simply executes without need for confirmation.     

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
[cs15lwi23ama@ieng6-201]:~:552$ ls
list-examples-grader  perl5  test
[cs15lwi23ama@ieng6-201]:~:553$ ls test/
test.txt  yes.txt
[cs15lwi23ama@ieng6-201]:~:554$ rm -ri test/
rm: descend into directory 'test/'? yes
rm: remove regular empty file 'test/test.txt'? yes
rm: remove regular empty file 'test/yes.txt'? yes
rm: remove directory 'test/'? yes
```
  
In this example, the -i option pairs with the -r option such that the user is prompted to confirm each item being deleted recursively by the rm command. Without the -i option, the command would simply execute without prompting as long as the files are not protected.    
  
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
  
In this example, the rm command deletes an empty folder with the -d option. Without the option, the command errors as rm cannot remove directories unless options allow it to.    
  
Example 2:   
```
[cs15lwi23ama@ieng6-201]:~:567$ ls
empty1  empty2  list-examples-grader  nonempty1.txt  perl5
[cs15lwi23ama@ieng6-201]:~:568$ rm -d empty1 empty2 nonempty1.txt
```

In this example, the rm command is able to delete empty folders along with files because the -d option is present. Without it, only the file would be deleted and the folders would remain. 

This option can be useful when trying to specify directories for rm to delete without wanting to use -r. It could also help detect and refrain from removing folders that are not empty. This option may also help you clear out your workspace by allowing you to remove empty folders from command line.     
  
Source: https://man7.org/linux/man-pages/man1/rm.1.html  
