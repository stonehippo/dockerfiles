# Pattern Lab Standard, Mustache Edition

[Pattern Lab](http://patternlab.io) helps build thoughtful, pattern-driven user interfaces using atomic design principles.

## Usage

This is the default version of Pattern Lab, and is available under the `latest` and `php-mustache` tags. You can get it going simply by running

```
$ docker run -d -p 8080:8080 --name pattern-lab stonehippo/pattern-lab-2
```

This pulls that default tag, which is `latest`. It's also possible to get this with the version specific tag:

```
$ docker run -d -p 8080:8080 --name pattern-lab stonehippo/pattern-lab-2:php-mustache
```

Containers created by this image include a copy of the starterkit project, so you start looking at Pattern Lab right away. After the container starts, point your browser of choice at `http://localhost:8080`.

You can also override the volume used to point to the Pattern Lab source, and point it to an external Pattern Lab instance, e.g. you local copy of a company pattern library.

```
$ docker run -d -p 8080:8080 -v $(pwd)/source:/opt/pattern-lab/source/ stonehippo/pattern-lab-2
```

For more info on this edition of Pattern Lab, see [Pattern Lab Standard, Mustache Edition](https://github.com/pattern-lab/patternlab-php).
