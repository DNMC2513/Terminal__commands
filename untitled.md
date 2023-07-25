# Basic Commands
**Review**: a mixture of both cmdlets and CommandPrompt commands to work in Microsoft PowerShell

OUTLINE:
1. A directory?
a. What is a directory?
b. Command to print the current directory on the screen:
c. Rules to call out directories containing spaces ' ':
d. Move to a dir:
e. Rules to call out a directory:
- Of a file that is inside the smallest folder of the dir:
- Of a file that contains the smallest folder of the dir:
- Of a file that is not on the same path leading to the dir:

2. Working with a directory (folders & files):
a. Create a new directory:
b. Move to the the target directory:
c. Show the content within a directory:
- Normal way:
- Files of the same format:
- Include the contents of sub-folder files in a normal way:
- Include the contents of sub-folder files in a tree paradigm:
- All and include hidden files:
- Only hidden files:

d. Remove a directory:
- Normal way:
- Remove the unempty files:

3. Working with files:
a. Show the content within a file:
- Cmd Commands
- PowerShell Commands (Cmdlet)

b. Create a new file:

c. Copy a file:
d. Move a file to a new folder:
e. Assign the output of a command to a file:
f. Compare files:
g. Remove a file:


## 1. A directory?

### a. What is a directory?
- A directory is the location of a folder/file, which is the combination of its name and all folders containing it divided by either '\'.

- eg:
```shell 
C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Computing_terminologies
```
- A directory is also referred to the folder that it represents.   
- A directory is also called as a `dir`.

### b. Command to print the current directory on the screen:
```shell
pwd
```

c. Rules to call out directories containing spaces ' ':
- Normally, we cannot work with a file that contains spaces:
    - eg:
```shell
PS C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Computing_terminologies> cd Test 1 
Set-Location : A positional parameter cannot be found that accepts argument '1'.
At line:1 char:1
+ cd Test 1
+ ~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Set-Location], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SetLocationCommand
                                                                                                 
```

- There are two solutions to this problem:
    - Enclose the dir with `"  "`:

```shell
PS C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Computing_terminologies> cd "Test 1"                   
```
    
    - Add an grave_accent or backtick before every space:
```shell
PS C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Computing_terminologies> cd Test` 1                                                                                               
```    
    

d. To move to a dir:
```shell
cd [dir_name]
```

e. Rules to call out a directory:
- Of a dir that is inside the smallest folder of the dir:
```shell
cd [dir_name]

#or use the tilde ~:
cd ~\dir_name

```

- Of a file that contains the smallest folder of the dir:
Use the .. to represent each folder that you have to step back
```shell
PS C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Computing_terminologies> cd ..\..

PS C:\Users\Admin\AppData\Roaming\Python\Python310>
```

- Of a file that is not on the same path leading to the dir:
```shell
C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Computing_terminologies> cd [The_WHOLE_dir]
```

## 2. Working with a directory (folders & files):
### a. Create a new directory:
```shell
New-Item -Path 'new.txt'

#or:
New-Item -Path 'abd.txt' -f
#to create a file even if a file of the same name already exists
```

### b. Move to the the target directory:
```bash
move [file_name] [target_folder]
```

### c. Show the content within a directory:
- Normal way:
```shell
dir

#all the files of the same format (same ending):
dir *.png

# Include the contents of sub-folder files in a normal way:
dir -s

#Include the contents of sub-folder files in a tree paradigm:
tree /F

# All and include hidden files:
dir -Force

#Only hidden files:
dir -Hidden
```

## d. Remove a directory:
```shell
#Normal way:
rmdir [dir]

#Remove the unempty files:
rm -r -fo [dir]
```
- The `-r` flag is to indicate that this task will be conducted recursively.
- The `-fo` flag is to escalate the effect of the command in case `-r` is not enough to make the system delete all the files.


## 3. Working with files:
### a. Show the content within a file:
```shell
#Cmd Commands:
type abc.txt

#PowerShell Commands (Cmdlet):
Get-Content abc.txt
```

### b. Create a new file:
```shell
New-Item -Path 'abd.txt'

#or
New-Item -Path 'abd.txt' -f
#to create a file even if a file of the same name already exists
```

### c. Copy a file:
```shell
copy [file] [new_folder]
```

### d. Move a file to a new folder:
```bash
move Git.ipynb C:\Users\Admin\AppData\Roaming\Python\Python310\Scripts\Git
```

### e. Assign the output of a command to a file:
```shell
$var1 = type Test1.txt

$var2 = Get-Content Test2.txt
```

### f. ompare files:
```shell
$var1 = type Test1.txt
$var2 = Get-Content Test2.txt
diff $var1 $Var2
```

### g. Remove a file:
```shell
del [dir]
```
