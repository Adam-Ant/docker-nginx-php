# docker-nginx-php
This is a dockerfile based on Alpine Linux to run PHP and Nginx together.
##Run It
To create a basic server, with nginx configs mounted at /config on the host, with the root directory mounted at /webroot on the host, use:

```
docker run -d -p 80:80 -v /webroot:/var/www -v /config:/etc/nginx/conf.d adamant/nginx-php
```

##Custom Configs
This repo is already configured to accept custom Nginx configs and locations. 

You **must** include the line `include /etc/nginx/common.conf;` within the server block to make sure PHP is configured correctly. For a basic example of this, see [default.conf](https://github.com/Adam-Ant/docker-nginx-php/blob/master/configs/default.conf)
