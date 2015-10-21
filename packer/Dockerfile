FROM alpine:3.2

RUN apk --update add go git alpine-sdk bzr mercurial
ENV GOPATH /go
ENV PATH /go/bin:$PATH

RUN go get -u github.com/mitchellh/packer
RUN cd $GOPATH/src/github.com/mitchellh/packer && \
    git stash && \
    make updatedeps
RUN apk add bash
RUN cd $GOPATH/src/github.com/mitchellh/packer && make
RUN go test ./... 
CMD ["go","run","main.go"]
