**A sample Docker workflow with Node.js, Redis and NGiNX**
[![Circle CI](https://circleci.com/gh/CostaRicaChc/docker.svg?style=svg)](https://circleci.com/gh/CostaRicaChc/docker)

In VirtualBox share your project root dir as 'dwf' (or whatever you like)

SSH in to the boot2docker VM

    boot2docker ssh

Build docker-compose container (this seems to be the easiest route in Windows)

    docker build -t docker-compose github.com/docker/compose

Mount your host drive (mine would not automount)

    sudo mkdir -p /dwf
    sudo mount -t vboxsf dwf /dwf
    cd /dwf

Create an alias for docker-compose (nice to have)

    alias dc='docker run --rm -i -t -v /var/run/docker.sock:/var/run/docker.sock -v `pwd`:`pwd` -w `pwd` docker-compose'

Run the alias to launch the app

    dc up

Hit the (**boot2docker ip**) at port 8080

Commit something and Circle CI will build and run your tests

TODO: Continous deployment

:musical_note: :musical_note: :musical_note: :musical_note: :musical_note: :musical_note: :musical_note:

    





