FROM alpine/git as git

USER root
WORKDIR /go
RUN git clone https://github.com/meysamdevops/jenkinstry.git

FROM golang:1.10-alpine as golang

USER root
WORKDIR /go
COPY  --from=git /go/jenkinstry/ /go/
RUN go build main.go

FROM jenkins/inbound-agent

USER root
WORKDIR /go
COPY --from=golang /go/main /go/






