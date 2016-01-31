## node-phantomjs Dockerfile

This builds a container with nodejs 5.5 and phantomjs 1.9.8 installed.
The container can be used for node projects that require [svgexport](https://github.com/shakiba/svgexport) to convert SVG files to PNG.

Credit to:
* https://github.com/TrackMaven/node-phantomjs
* https://github.com/nodesource/docker-tutorial

## How to use

View [nodesource tutorial](https://nodesource.com/blog/dockerizing-your-nodejs-applications/).

Create a Dockerfile in your project directory root with the following:

```
FROM infiniteblue/node-phantomjs

ADD package.json package.json
RUN npm install
ADD . .

EXPOSE 3000
CMD ["node", "app.js"]
```

All your project files are saved in WORKDIR which is `/usr/src/app/`