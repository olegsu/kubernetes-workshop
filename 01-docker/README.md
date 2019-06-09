# Docker recap
1. Clone the docker-chat application
    `git clone https://github.com/ageapps/docker-chat && cd docker-chat`
2. Lets build the docker-chat image from source file
    `docker build -t chat app`
    Now we have image on the machine called `chat` which we will use
3. Run mongo database
    `docker run -d --name db mongo`
    * `-d` option to run in the the backgroud
    * `--name` give a container a logical name
docker run -d --name db mongo
4. Run the build image we build just before
    `docker run --link db -p 80:3000 -d chat`
    * `-d` option to run in the the backgroud
    * `-p` to forward all the trafic from local port 80 to container port 3000, which the application listens on
    * `--link` to make the mongodb accessible via dns resolution

# Summary 
```bash
git clone https://github.com/ageapps/docker-chat && cd docker-chat
docker build -t chat app
docker run -d --name db mongo
docker run --link db -p 80:3000 -d chat
```