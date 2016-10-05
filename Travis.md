Encrypt private key for travis-ci
-------------------------

```sh
ssh-keygen -t rsa -b 4096 -C 'pk-deployment@travis-ci.com' -f ./key_14_rsa
travis encrypt-file key_14_rsa --add
ssh-copy-id -i key_14_rsa.pub <username>@<host> // copy key_14_rsa.pub to server (file ~/.ssh/authorized_keys/)

travis encrypt USERDEV=azureuser --add

rm -f key_14_rsa key_14_rsa.pub
git add key_14_rsa.enc .travis.yml
```