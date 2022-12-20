# GNOME Editor

## Build
Via GitHub repository
```bash
$ docker build --tag alireaza/gedit:$(date -u +%Y%m%d) --tag alireaza/gedit:latest https://github.com/alireaza/gedit.git
```

## Run
```bash
$ docker run \
--interactive \
--tty \
--rm \
--mount="type=bind,source=/tmp/.X11-unix,target=/tmp/.X11-unix" \
--env="DISPLAY=$DISPLAY" \
--device="/dev/dri:/dev/dri" \
--env="NO_AT_BRIDGE=1" \
--env="TZ=$(cat /etc/timezone)" \
--mount="type=bind,source=$(pwd)/udocker,target=/home/udocker" \
--name="gedit" \
alireaza/gedit
```

