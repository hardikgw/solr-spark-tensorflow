# TensorFlow with Spark processing and Solr data
### Running Tensorflow on Docker (for model validation)

`run -itd --name=tf -p 8888:8888 -p 6006:6006 -v $(pwd)/search-py:/home gcr.io/tensorflow/tensorflow /bin/sh`
#### Options
- "-itd" : interactive terminal demon
- "-p 8888:8888" : Jupyter
- "-p 6006:6006" : TensorBoard
- "-v ...." : localfolder relative to current dir exposed to /home in container
- "/bin/sh" : override default container command
