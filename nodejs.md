### Install nodejs via source

```
# sudo apt-get install build-essential

ver=6.9.2
wget -c https://nodejs.org/dist/v$ver/node-v$ver.tar.gz #This is to download the source code.
tar -xzf node-v$ver.tar.gz
cd node-v$ver
./configure && make && sudo make install
```