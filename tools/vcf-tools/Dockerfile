FROM ubuntu:15.04

RUN apt-get update && apt-get install -y curl g++ pkg-config zlib1g-dev python
WORKDIR /opt
RUN curl -L -O https://github.com/vcftools/vcftools/releases/download/v0.1.14/vcftools-0.1.14.tar.gz
RUN tar xvzf vcftools-0.1.14.tar.gz && cd vcftools-0.1.14 && ./configure && make && make install
ADD hgsc_vcf /opt/hgsc_vcf
ADD merge_vcfs.py /opt/merge_vcfs.py
