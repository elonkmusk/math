ERSION 0.8
FROM ubuntu:22.04
WORKDIR /go-workdir

build:
    COPY main.go .
    COPY math .
    COPY run.sh .
    RUN ls -la
    RUN bash run.sh
    RUN go build -o output/example main.go
    SAVE ARTIFACT output/example

docker:
    COPY +build/example .
    ENTRYPOINT ["/go-workdir/example"]
    SAVE IMAGE go-example:latest

