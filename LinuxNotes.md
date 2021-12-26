# Installing Linux On Windows

```wsl --install -d <Linux distribution>```
* Need to run in Administrator mode.
* e.g. ```wsl --install -d Ununtu```

```wsl --list --online```
* Lists all the Linux distributions available for installation

# Linux Directory Structure

# Handy Shortcuts

```Ctrl+L```     Clear screen

# Redirection


# Handy Commands
```ls -a```
* Lists all the hidden files, i.e. files beginning with ```.```

```mkdir -p <dir>/<subdir>/<subdir>```
* Allows us to create nested folders.

```touch <filename 1> <filename 2> ... <filename n>```
* if <filename> doesn't exist touch will create it
* if <filename> does exist, then it will create it  

```rm```
* can delete files and directories
* by default only deletes a directory if it is empty
* can delete files or directories
* ```-v``` option is a nice way to confirm what was deleted
* ```-i``` interactive mode, asks for confirmation of each directory/file to delete
  
```xdg-open```

```head <filename>```
by default it prints out the top 10 lines of the file

```tail```


