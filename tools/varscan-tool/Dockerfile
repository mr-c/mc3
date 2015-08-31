FROM    java


RUN     apt-get update
RUN     apt-get install -y wget samtools build-essential git-core cmake zlib1g-dev libncurses-dev

WORKDIR /opt
ENV     JAVA_JAR_PATH   /opt
RUN     wget --no-check-certificate -O VarScan.v2.4.0.jar https://github.com/dkoboldt/varscan/blob/ed3227992f31725548d6106dc7fcd0bd8879ff1e/VarScan.v2.4.0.jar?raw=true && mv VarScan.v2.4.0.jar VarScan.jar

RUN wget https://github.com/genome/bam-readcount/archive/v0.7.4.tar.gz && tar xvzf v0.7.4.tar.gz && rm v0.7.4.tar.gz
RUN cd /opt/bam-readcount-0.7.4 && mkdir build && cd build && cmake ../ && make deps && make -j && make install
