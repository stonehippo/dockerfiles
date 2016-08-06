# Pattern Lab Node, Gulp Edition

[Pattern Lab](http://patternlab.io) helps build thoughtful, pattern-driven user interfaces using atomic design principles.

## Usage

This is the Node version of Pattern Lab, with the gulp wrapper. It is available under the `node-gulp` tag. You can get it going simply by running

```
$ docker run -d -p 3000:3000 --name pattern-lab stonehippo/pattern-lab-2:node-gulp
```

After the container starts, point your browser of choice at `http://localhost:3000`. There's no starter kit included, so you won't see much.

The Browsersync UI is availalble on port 3001.

You can also override the volume used to point to the Pattern Lab source, and point it to an external Pattern Lab instance, e.g. you local copy of a company pattern library.

```
$ docker run -d -p 3000-3001:3000-3001 -v $(pwd)/source:/opt/pattern-lab/source/ stonehippo/pattern-lab-2:node-gulp
```

For more info on this edition of Pattern Lab, see [Pattern Lab Node, Gulp Edition](https://github.com/pattern-lab/edition-node-gulp).
