## Spark History Server Docker Image

This repo contains the Dockerfile and associated dependencies to build the image for the Spark history server [Helm chart](https://github.com/helm/charts/tree/master/stable/spark-history-server).  Spark history server does not require a separate image other than an image that contains a Spark build. But extra dependencies need to be baked in the image in order to enable the history server to communicate with Google Cloud Storage or AWS S3, if the user chooses to use one of those options as backend storage.

The Docker image corresponding to this repo is `lightbend/spark-history-server`. It's also the default image used in the Helm chart. Feel free to build your own image with your custom build of Spark or dependencies. The Helm chart also supports setting `image.repository` and `image.tag` to install the chart with your custom image.

### Google Cloud Storage

The [Cloud Storage connector](https://cloud.google.com/dataproc/docs/concepts/connectors/cloud-storage) is included in the image to enable the history server to read from Spark event logs in GCS.

### S3

To-do

 