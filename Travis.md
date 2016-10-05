Encrypt private key for travis-ci
-------------------------

```sh
ssh-keygen -t rsa -b 4096 -C 'pk-deployment@travis-ci.com' -f ./key_14_rsa
travis encrypt-file key_14_rsa --add
ssh-copy-id -i key_14_rsa.pub <username>@<host> // copy key_14_rsa.pub to server (file ~/.ssh/authorized_keys/)

travis encrypt USERDEV=<username> --add

rm -f key_14_rsa key_14_rsa.pub
git add key_14_rsa.enc .travis.yml
```

After that, you can run ssh to server via config in `.travis.yml`

```yml
after_success:
- eval "$(ssh-agent -s)"
- chmod 600 $TRAVIS_BUILD_DIR/key_14_rsa
- ssh-add $TRAVIS_BUILD_DIR/key_14_rsa
- ssh -i $TRAVIS_BUILD_DIR/key_14_rsa $USERDEV@52.187.79.155 "<command to run on remote server>"
```