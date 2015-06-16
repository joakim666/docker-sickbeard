# docker sickbeard with periscope

This is a Dockerfile to set up [Sickbeard](http://sickbeard.com/) with [Periscope](https://code.google.com/p/periscope/) for automatic downloading of subtitles.

Build from docker file

```
git clone git@github.com:timhaak/docker-sickbeard.git
cd docker-sickbeard
docker build -t sickbeard .
```

docker run -d -h *your_host_name* -v /*your_config_location*:/config  -v /*your_videos_location*:/data -p 8081:8081 sickbeard


## Configuration

Create a script file like this:

	#!/bin/sh
	/usr/local/bin/periscope "$1" -l en --force

then add the script file in the Sickbeard configuration file, config.ini, as the script for the extra_script field

	extra_scripts =



