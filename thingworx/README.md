# ThingWorx

[PTC ThingWorx](http://thingworx.com) is an IoT Application Enablement Platform.

This image creates a container built around Tomcat 8.5 and deploying an instance of PTC ThingWorx.

*Important*: This repo doesn't include `Thingworx.war`. You'll need to download the ThingWorx Foundation Server yourself from the [ThingWorx DevZone](http://developer.thingworx.com), then copy the .war into `/webapps` before building the image.

## Build

Run the following in the root directory of this project.

```
$ docker build -t stonehippo/thingworx .
```

## Usage

```
$ docker run --it -rm -p 8080:8080 stonehippo/thingworx
```
