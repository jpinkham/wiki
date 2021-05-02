# Docker

## Docker

It is starting to be quite a pain to run all the many things I want to install/try out, due to all the dependencies and whatnot, and I'd prefer some isolation between things and stop mucking up system libraries and blah blah blah $reasons.

### Basic knowledge

* Install Docker if it doesn't already exist
* If it does exist, start the Docker engine, if not started already
  * service docker start

    OR

  * /etc/init.d/docker start

### Creating a Docker container from a Dockerfile

Luckily more and more open source projects are including a Dockerfile -- w00t

1\) check the README, which usually has the needed commands 2\) Build the container using the provided Dockerfile EXPERT level: Modify the Dockerfile to strip to bare essentials, especially base image, before building 3\) PROFIT...no really, finish building this list, jp

#### Example: Nikto

```text
git clone https://github.com/sullo/nikto.git
cd nikto
docker build -t sullo/nikto .
# Call it without arguments to display the full help
docker run --rm sullo/nikto
# Basic usage
docker run --rm sullo/nikto -h http://www.example.com
# To save the report in a specific format, mount /tmp as a volume:
docker run --rm -v $(pwd):/tmp nikto -h http://www.example.com -o /tmp/out.json
```

## Common commands

#### List Docker CLI commands

```text
docker
docker container --help
```

#### Display Docker version and info

```text
docker --version
docker version
docker info
```

#### Execute Docker image

```text
docker run hello-world
```

#### List Docker images

```text
docker image ls
```

#### List Docker containers

```text
docker container ls         # all running
docker container ls --all   # all, regardless of state
docker container ls -aq     # all, but quiet
```

Source: [https://docs.docker.com/get-started/](https://docs.docker.com/get-started/)

To show only running containers use the given command:

`docker ps`

To show all containers use the given command:

`docker ps -a`

To show the latest created container \(includes all states\) use the given command:

`docker ps -l`

To show n last created containers \(includes all states\) use the given command:

`docker ps -n=-1`

To display total file sizes use the given command:

`docker ps -s`

Source: [https://stackoverflow.com/questions/16840409/how-to-list-containers-in-docker](https://stackoverflow.com/questions/16840409/how-to-list-containers-in-docker)

```text
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyhello" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
```

Source: [https://docs.docker.com/get-started/part2/](https://docs.docker.com/get-started/part2/)



## Finding pre-built Docker containers

```
docker search [--filter is-official=true] <search term>
```
