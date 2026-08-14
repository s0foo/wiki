# Disk Usage
## Partitions usage
df -h

# Xmodmap
** xmodmap -e 'keycode 37=Control_L' or NoSymbol
Disable the corresponding key
** xev -event keyboard
Obtain keycode for keys

# Grep
## grep -i <pattern> */file
To search the pattern in all files of the current directory or in a specific file.
## grep -r <pattern> .
To recursively search the pattern in all files.

# Tar
## Creating an archive
tar cvf archive_name.tar /folder/path file1 file2
## Extracting an archive
tar xvf archive_name.tar
## Listing an archive
tar tf archive_name.tar
