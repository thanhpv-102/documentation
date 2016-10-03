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
