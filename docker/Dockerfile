FROM gcr.io/tensorflow/tensorflow
RUN \
	apt-get update &&\
	apt-get install -y wget vim bash-completion unzip &&\
	wget https://storage.googleapis.com/google-code-archive-source/v2/code.google.com/word2vec/source-archive.zip &&\
	apt-get install -y python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose &&\
	apt-get install -y python-dev python-pip g++ libopenblas-dev git &&\
	pip install Theano &&\
 	cd /home &&\
 	wget https://storage.googleapis.com/google-code-archive-source/v2/code.google.com/word2vec/source-archive.zip
