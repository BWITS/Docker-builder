FROM alpine:3.2

RUN apk --update add go git

ENV GOPATH /go
ENV PATH /go/bin:$PATH

RUN go get github.com/CenturyLinkLabs/imagelayers
RUN go get github.com/tools/godep
WORKDIR $GOPATH/src/github.com/CenturyLinkLabs/imagelayers
RUN godep restore
RUN go test ./... 
CMD ["go","run","main.go"]
