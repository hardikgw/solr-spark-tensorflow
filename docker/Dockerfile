FROM gcr.io/tensorflow/tensorflow:latest-py3
WORKDIR /
RUN \
	echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  	add-apt-repository -y ppa:webupd8team/java && \
  	apt-get update && \
  	apt-get install -y oracle-java8-installer && \
  	rm -rf /var/lib/apt/lists/* && \
  	rm -rf /var/cache/oracle-jdk8-installer && \
	apt-get update &&\
	apt-get install software-properties-common && \
	apt-get install -y wget curl vim bash-completion unzip openssh-server && \
	echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list && \
	curl https://bazel.build/bazel-release.pub.gpg | sudo apt-key add - && \
	apt-get update && sudo apt-get install bazel && \
	apt-get install -y python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose && \
	apt-get install -y python-dev python-pip g++ libopenblas-dev git && \
	pip install spaCy && \
	python3 -m spacy.en.download all && \
	pip install pyLDAvis scipy scipy gensim nltk bokeh && \
	pip install -U scikit-learn && \
	apt-get update && \
	apt-get clean && \
 	mkdir /opt/logs && \
	touch start.sh && \
	chmod 755 start.sh && \
	echo "#!/bin/sh" >> start.sh && \
	echo "nohup tensorboard --logdir=/data/logs > tb.out & nohup ./run_jupyter.sh >jupyter.out &" >> start.sh && \
	echo "tail -f jupyter.out" >> start.sh
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle
EXPOSE 6006 8888
CMD ["./start.sh"]
