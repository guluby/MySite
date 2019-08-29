# Linux Shell Notes
Besides basic linux command line, summary of some useful concept/syntax 

Command Line-> shell -> kernel -> Hardware

### Pipeline
Pipe combines two or more commands, the output of one serves as input to the next one `command_1 | command_2 | ... | command_n`

Example:
>Source: https://www.geeksforgeeks.org/piping-in-unix-or-linux  

>print file head and tail  
`cat file.txt | head -5 | tail -5`

>list file, find particular files and print all lines matching a particular pattern in matching files  
`ls -l | find ./ -type f -name "*.txt" -exec grep "program" {} \;`

> Read the particular entry, get info and store in a file.  
` cat result.txt | grep "Some info" | tee file2.txt`

### grep
Grep searches a file for a particular pattern of characters, and displays all lines that contain that pattern. `grep [options] pattern [files]`

Options Description  
>**-c** : This prints only a **count of the lines** that match a pattern 
* Example:`grep -c "linux" text.file` will return the number of lines that match the given string

>**-l** : **Display file name only**
* Example: `find . -exec grep -l foo {} +` will show the file name that contains text 'foo', `+` can be replaced by `\;`

>**-i** : Ignores, **case insensitive search**  
* Example:`grep -i 'LiNux' text.file` will return the lines have 'linux','Linux' and etc.
 
>**-n** : Display the matched lines and their **line numbers**.  
* Example: `grep -n "linux" text.file` will return the line number and the matched lines

>**-v** : This prints out all the lines that do not matches the pattern
* Example:`grep -v "linux" text.file` **Inverting the pattern match** and display the lines do not match the pattern

>Add **^** in front of or **$** at the end of a string, will match lines that **start/end with** a string pattern
* Example `grep "^linux" text.file` will print lines that start with _linux_(the searched object)
* Example `grep "linux$" text.file` will print lines that ends with _linux_(the searched object)

>Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux  


### find
>Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples 

Find file within specified dir and perform subsequent operations
`find [where to start searching from] [-options] [what to find]`
Options Description
>**-name** or **-iname**(case insensitive) to search a file with specific name or a pattern
* Example: `find Dir/ -name *.py` will find all .py files in Dir directory

>**-exec** after find the file, execute some command line
* Example: `find Dir/ -name text.file -exec grep "string" {} \;` will find the desired file and display lines contain searched strings
* Example: `find Dir/ -name test.file -exec rm -i {} \;` find the test.file under Dir and let the usr choose whether to delete the file.{} is the filename found.
* Example: `find Dir -type f -name *.file -exec grep "Strings" {} +` Search text within multiple files(found by find-command)

>**-type** find file by type, type option: f -regular file, d -directory, I -symbolic link, etc

>**-size** find file by size, c -bytes, k -kilobytes, M -Megabytes, G -Gigabytes.
* Example: `find / -size +1000M`

>**-empty** find all empty folders and files

### cat
concatentate command, can view one/multiple files (with line number), append text/files to another file. Here are some common task examples.

* View one file or multipe files
    ```bash
    cat file1
    cat file1 file2
    ```
  View the last lines first
    ```bash
    tac file1
    ```
* Copy a file or append contents to another file
    ```sh
    cat file1 >> newfile
    ```
* Add text to the end of file
    ```bash
    cat >> filename
    Some text
    ```
   Then Ctrl+D. This might by easier with `echo` command
   ```sh
   echo 'some text' >> /path/to/file
   ```