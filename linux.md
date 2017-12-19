Add folder to $PATH in linux
------------------------

```
if [ -d "$HOME/bin" ] ; then #check folder $HOME/bin existed, then include to $PATH variable
  PATH="$PATH:$HOME/bin"
fi

# Add more folder
if [ -d "$HOME/other/bin" ] ; then 
  PATH="$PATH:$HOME/other/bin"
fi
```

Find big size file in path
-------------------

```
find /<path> -printf '%s %p\n'| sort -nr | head -10
```

How to Find Biggest Files and Directories in Linux
---------------------------

Run the following command to find out top biggest directories under /home partition.

```
du -a /home | sort -n -r | head -n 5
```

If you want to display the biggest directories in the current working directory, run:

```
du -a | sort -n -r | head -n 5
```

Some of you would like to display the above result in human readable format. i.e you might want to display the largest files in KB, MB, or GB.

```
du -hs * | sort -rh | head -5
```

To display the largest folders/files including the sub-directories, run:

```
du -Sh | sort -rh | head -5
```
