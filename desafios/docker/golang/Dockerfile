FROM golang:1-alpine AS build_base

WORKDIR /go/src/app

COPY . .

RUN go mod init && \
    go build -o server .

FROM scratch

WORKDIR /go/src/app

COPY --from=build_base /go/src/app/server .

CMD ["/go/src/app/server"]