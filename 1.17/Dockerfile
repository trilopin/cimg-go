# vim:set ft=dockerfile:

FROM cimg/base:2021.07

LABEL maintainer="Community & Partner Engineering Team <community-partner@circleci.com>"

ENV GO_VERSION=1.17.1

# Install packages needed for CGO
RUN sudo apt-get update && sudo apt-get install -y --no-install-recommends \
		g++ \
		libc6-dev && \
	wget https://www.python.org/ftp/python/3.9.7/python-3.9.7-macosx10.9.pkg && \
	sudo rm -rf /var/lib/apt/lists/* && \
	curl -sSL "https://golang.org/dl/go${GO_VERSION}.linux-amd64.tar.gz" | sudo tar -xz -C /usr/local/ && \
	mkdir -p /home/circleci/go/bin

RUN curl -sSL "https://github.com/gotestyourself/gotestsum/releases/download/v1.7.0/gotestsum_1.7.0_linux_amd64.tar.gz" | \
	sudo tar -xz -C /usr/local/bin gotestsum

ENV GOPATH /home/circleci/go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
