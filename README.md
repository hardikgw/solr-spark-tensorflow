# TensorFlow with Spark processing and Solr data
### Running Tensorflow on Docker (for model validation)

`sudo docker run -it -p 8888:8888 -p 6006:6006 --name=tf -v $(pwd)/data:/data -e PASSWORD=password cithub/tf`
#### Options
- "-itd" : interactive terminal demon
- "-p 8888:8888" : Jupyter
- "-p 6006:6006" : TensorBoard
- "-v ...." : localfolder relative to current dir exposed to /home in container
- "-e PASSWORD=password" : Password for Jupyter notebook
- "/bin/sh" : override default container command
