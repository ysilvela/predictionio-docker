# PredictionIO docker container
Docker container for PredictionIO-based machine learning services

[![Docker build](http://dockeri.co/image/ysilvela/predictionio-docker)](https://registry.hub.docker.com/r/ysilvela/predictionio-docker/)

[PredictionIO](https://prediction.io) is an open-source Machine Learning
server for developers and data scientists to build and deploy predictive
applications in a fraction of the time.

This container uses Apache Spark, HBase and Elasticsearch.
Use it interactively for development:

```Bash
$ docker run -it -v $HOME/MyEngine:/MyEngine ysilvela/predictionio /bin/bash
```

Or create your own deployable docker container:

```Dockerfile
FROM ysilvela/predictionio

ADD MyEngine /MyEngine

EXPOSE 8000

ADD run.sh /run.sh

ENTRYPOINT /run.sh
```

and run.sh:

```Bash
#!/bin/bash

set -e

pio-start-all
cd /MyEngine
pio build --verbose
pio deploy
```
