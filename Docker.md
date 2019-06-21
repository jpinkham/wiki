#Docker

It is starting to be quite a pain to run all the many things I want to install/try out, due to all the dependencies and whatnot, and I'd prefer some isolation between things and stop mucking up system libraries and blah blah blah $reasons.

# Basic knowledge
* Install Docker if it doesn't already exist
* If it does exist, start the Docker engine, if not started already
  * service docker start
  OR
  * /etc/init.d/docker start


## Creating a Docker container from a Dockerfile
Luckily more and more open source projects are including a Dockerfile -- w00t

1) check the README, which usually has the needed commands
2) Build the container using the provided Dockerfile
EXPERT level: Modify the Dockerfile to strip to bare essentials, especially base image, before building
3) 


### Example: Nikto
```
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

