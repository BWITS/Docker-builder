FROM golang

RUN apt-get install git bzr mercurial
ENV GOPATH /go
ENV PATH /go/bin:$PATH

RUN go get -u github.com/mitchellh/packer

WORKDIR $GOPATH/src/github.com/mitchellh/packer
RUN git stash && \
    make updatedeps
RUN make
RUN go test ./... 
CMD ["go","run","main.go"]
