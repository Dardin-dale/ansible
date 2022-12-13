# ansible
ansible files to start up a development environment on a new container/computer using ubuntu/apt

based on FEM's course by ThePrimeagen 

Testing with provided docker:

step 1 - clone this repo

step 2 - build test docker container

run ./build-docker (shell script)

step 3 - run docker

`docker run --rm -it nvim computer bash`

step 4 - run ansible

`ansible-playbook local.yml`
