# Linux Tweet App

This is very simple NGINX website that allows a user to send a tweet.  If you have Jenkins installed and have setup a webhook in GitHub, Jenkins will automatically create and push your new Docker image to your Docker Hub repo on a Git commit.  Pushing to Nexus -- WIP.

## To use it:

Build it:
`docker build -t linux_tweet_app .`

Run it:
`docker container run --detach -p 80:80 linux_tweet_app`

## Dockerfile:

The `FROM` command is using `nginx` as the base image.  `COPY` copies 2 files.  `EXPOSE` exposes a port.  `CMD` will run nginx in the foreground.

## Jenkinsfile:

This file is divided into 4 stages: clone, build, test, and push.  
- The 'clone' stage checks out the repo from GitHub.  
- The 'build' stage builds the image and stores it in a variable called 'app'.   Change 'hosch3016' to your Docker Hub repo and 'linux_tweet_app' to your image name.  
- The 'test' stage is a placeholder as of now, currently just echos "Tests passed".  
- Finally the 'push' stage where it pushes you image to your Docker Hub repo.  Make sure to change 'dockerhub' to match the "ID" of the credential you created in Jenkins for your DockerHub account.

(Note: Create a credential in Jenkins for your DockerHub repo/acct.  Provide the username, password, and an ID of your choseing, just make note of its value).
