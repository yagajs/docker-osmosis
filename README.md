# Osmosis for Docker

Osmosis docker image from the [YAGA Development-Team](https://yagajs.org).

## Supported tags

* `0.45`, `latest`

## What is Osmosis

[Osmosis](http://wiki.openstreetmap.org/wiki/Osmosis)is a command line Java application for processing OSM data. The
tool consists of pluggable components that can be chained to perform a larger operation. For example, it has components
for reading/writing databases and files, deriving/applying changes to data sources, and sorting data, (etc.). It has
been written to easily add new features without re-writing common tasks such as file and database handling.

## Run container

The container just ships osmosis and is not able to run without any additional commands.

Here are some examples how you can use this image *(For more information visit the 
[detailed usage page of the osmosis project](http://wiki.openstreetmap.org/wiki/Osmosis/Detailed_Usage_0.45))*:

You can run the container with a command like this:

```bash
# Import from and export to osm-xml
docker run -v /absolute/path/to/osm-data:/osm-data yagajs/osmosis osmosis --read-xml file="/osm-data/planetin.osm" --write-xml file="/osm-data/planetout.osm"

# Import from pbf export to osm-xml
docker run -v /absolute/path/to/osm-data:/osm-data yagajs/osmosis osmosis --read-pbf "/osm-data/planetin.osm.pbf" --write-xml file="/osm-data/planetout.osm"
```

The container is bundled into the [official openJDK](https://hub.docker.com/_/openjdk/) image and pre-configured to work
with Postgis. For best experience, we recommend to use the [YAGA Postgis](https://hub.docker.com/r/yagajs/postgis/)
image.

## Contributing

You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull
requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a
[GitHub issue](https://github.com/yagajs/docker-osmosis/issues), especially for more ambitious contributions.
This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help
you find out if someone else is working on the same thing.