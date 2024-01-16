# Lab Report 1 - Remote Access and FileSystem 

* **`cd`**
  1. `cd` with no argument
     ![image](cd w:o argument .png)

     The working directory when this command ran is `/home`. Since no argument was given, the filesystem had no directory to change to, thus current directory remained the same. This output is not an error.
  3. `cd` with path to directory argument
     ![image](cd w directory argument .png)

     The working directory when this command ran is `/home/lecture1`. The filesystem has a file path that changed the current directory to the lecture1 directory. Since lecture1 was passed as an argument, it can be seen that the output indicates that we are in the lecture1 directory. This output is not an error. 
  5. `cd` with path to file argument
      ![image](cd w file argument .png)

     The working directory when this command ran is `/home/lecture1/README`. The filesystem has a file path which caused the output to display an error. It is an error because `cd` changes the directory, it cannot change the directory to a file. 
     
  
* **`ls`**
  1. `ls` with no argument
     ![image](ls w:o argument .png)
       The working directory when this command ran is `/home`. No argument was given so `ls` prints the current files/directories within `/home`. The only directory in `/home` is lecture1 which was printed, so the output is not an error. 
  3. `ls` with path to directory argument
     ![image](ls w directory argument .png)
       The working directory when this command ran is `/home/lecture1`. Since a path to a directory was passed into the filesystem, `/ls` printed out all files/directories in lecture1. The output is not an error. 
  5. `ls` with path to file argument
     ![image](ls w file argument .png)
       The working directory when this command ran is `/home/lecture1/README`. A path to a file was passed into the filesystem. However, `/ls` only prints out files/directories in the current directory. Since README is a file, the output indicates an error. 

  
* **`cat`**
  1. `cat` with no argument
     ![image](cat w:o argument.png)
       The working directory when this command ran is `/home`. No argument was passed so `cat` does not print out anything as we are still in the `/home` directory. The output is an error since `cat` only works with files, and not directories. 
  3. `cat` with path to directory argument
     ![image](cat w directory as argument .png)
       The working directory when this command ran is `/home/lecture1`. A path to a directory was passed into the filesystem. However, since we are still in a directory, we still get an error.
  5. `cat` with path to file argument
     ![image](cat w file argument .png)
       The working directory when this command ran is `/home/lecture1/README`. A path to a file was passed into the filesystem. This meant that since we are looking at a file, `cat` can print out the contents of README as seen. The output is not an error. 
     
