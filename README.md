# Don't Starve Together Dedicated Server Docker Image

They write their server setup instructions like sh*t, so we made this Docker image.

----------

## Project Status

**Working on new features, document not ready. Anything below is outdated.**

## Known Issues

 * On Docker environment which doesn't support UDP port forwarding, LAN only server cannot be used. (Still you can enable Steam punchthrough and search for your server in `Online` catalog. )

## Running

```shell
docker run -v ${HOME}/.klei/DoNotStarveTogether:/data -it jamesits/dst-server:latest
```

We recommend reserving 1GiB Memory for the server, plus 60MiB per active user.
 
## Server Configuration

**TODO**

### Instructions on Obtaining Server Token

Launch a steam client on a system with GUI, install Don't Starve Together, log in, press `~` button then type `TheNet:GenerateClusterToken()` then press enter. You'll find a `cluster_token.txt` under your client config directory. (See ["References"](#references) section below for more detailed instructions. )

If you use the Docker Compose way, or have `/data/dst` mounted to your host machine, **copy the FILE** `server_token.txt` (not its content) to that folder. Also you may set token in `settings.ini`.

In other cases, you can set ENV `DST_CLUSTER_TOKEN` using the content of your `cluster_token.txt`. Just open it use any text editor and **copy the CONTENT**.

## Build Docker image locally

(In most cases you don't need this; just pull the prebuilt image from Docker Hub.)

```shell
git clone https://github.com/Jamesits/docker-dst-server.git docker-dst-server
cd docker-dst-server
docker build . -t dst-server:latest
```

----------

## Maintainer

 * [James Swineson](https://swineson.me)
 * [@Arthur2e5](https://github.com/Arthur2e5)
 
## Thanks

 * [@MephistoMMM](https://github.com/MephistoMMM)
 * [@m13253](https://github.com/m13253)
 * [@wph95](https://github.com/wph95)
 * [DaoCloud](https://daocloud.io)
 * [CodeVS](http://codevs.cn/)
 
## License

    Don't Starve Together Dedicated Server Docker Image
    Copyright (C) 2015-2018 James Swineson (Jamesits) and Mingye Wang (Arthur2e5)

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, write to the Free Software Foundation, Inc.,
    51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

## References

 * [How to setup dedicated server with cave on Linux](https://steamcommunity.com/sharedfiles/filedetails/?id=590565473)
 * [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD)