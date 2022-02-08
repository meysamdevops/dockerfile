FROM alpine/git as git

WORKDIR /go
RUN git clone https://github.com/meysamdevops/jenkinstry.git

FROM golang:1.10-alpine as golang

WORKDIR /go
COPY  --from=git /go/jenkinstry/ /go/
RUN go build main.go

FROM jenkins/inbound-agent

WORKDIR /go
COPY --from=golang /go/main /go/
CMD ["./main"]





