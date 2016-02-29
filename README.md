# PredictionIO docker container
Docker container for PredictionIO-based machine learning services

[![Docker build](http://dockeri.co/image/ysilvela/predictionio-docker)](https://registry.hub.docker.com/r/ysilvela/predictionio-docker/)

[PredictionIO](https://prediction.io) is an open-source Machine Learning
server for developers and data scientists to build and deploy predictive
applications in a fraction of the time.

This container uses Apache Spark, HBase and Elasticsearch.
Use it interactively for development.

You can do the pull and build at the same time using the next command:

```Bash
$ docker run -it -v $HOME/MyEngine:/MyEngine ysilvela/predictionio-docker /bin/bash
```

Or create your own deployable docker container:

```Dockerfile
FROM ysilvela/predictionio-docker

ADD MyEngine /MyEngine

EXPOSE 8000

ADD run.sh /run.sh

ENTRYPOINT /run.sh
```
Then you need to download your preferred template from https://templates.prediction.io/ choosing the appropiate template and following the installation instructions.

For example, if you choose the E-Commerce Recommendation template you can follow the steps indicated in the  [Quick Start Guide](https://docs.prediction.io/templates/ecommercerecommendation/quickstart/)
