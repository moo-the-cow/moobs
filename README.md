# moobs

**First stable version: 1.42**

If there are any issues please feel free to create a ticket and I will get to those eventually

Check out the [Wiki](https://github.com/moo-the-cow/moobot-obs/wiki) for details

## Pre-Requirements (windows)
+ OBS https://obsproject.com/download
+ Docker for Windows (it's important to check their requirements) https://docs.docker.com/docker-for-windows/install/
+ Router that can Port-Forward to your windows machine (also check windows firewall)


## Pre-Requirements (linux)
+ docker-ce
+ docker-compose

## Installation (mixed)
+ download https://github.com/moo-the-cow/moobs/archive/refs/heads/main.zip extract do a folder that will be used permamently
+ modify the `appsettings.json` to whatever you need
+ make sure docker for windows is started and the containers are switched to "linux containers" (see https://docs.docker.com/docker-for-windows/)
+ open a Terminal (suggestion: https://www.microsoft.com/store/productId/9N8G5RFZ9XK3 ) browse to that directory and type
```
docker-compose up -d
```
or just execute the bat file
