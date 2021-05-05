# Linux Tweet App

This is very simple NGINX website that allows a user to send a tweet. 

To use it:

Build it:
`docker build -t linux_tweet_app .`

Run it:
`docker container run --detach -p 80:80 linux_tweet_app`
