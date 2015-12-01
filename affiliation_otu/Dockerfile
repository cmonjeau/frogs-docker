############################################################
# Dockerfile to build FROGS affiliation_OTU deps
# Based on debian wheezy with RDPTools
############################################################

# Set the base image to debian wheezy with flash
FROM cmonjeau/rdptools

# Set noninterative mode
ENV DEBIAN_FRONTEND noninteractive
ENV PACKAGES perl util-linux ncbi-blast+ 

################## DEPENDENCIES INSTALLATION ######################

RUN apt-get update -y
RUN apt-get install -y ${PACKAGES}

################## AFFILIATION_OTU DEPENDENCIES ######################

RUN mkdir /root/affiliation_otu_deps
WORKDIR /root/affiliation_otu_deps
env PATH $PATH:/root/affiliation_otu_deps/

COPY bin/* ./
ADD affiliation_OTU_tpl.html .
ADD affiliation_OTU.py .

# RUN cp /root/RDPTools/classifier.jar .
RUN cp -r /opt/RDPTools/* .

###############################################################

MAINTAINER Monjeaud Cyril <Cyril.Monjeaud@irisa.fr>

