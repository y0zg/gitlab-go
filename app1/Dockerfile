FROM golang:1.10-alpine3.7 as build

WORKDIR /go/src/app1

COPY . .

RUN go build -o app1

FROM alpine:3.7

COPY --from=build /go/src/app/app1 /usr/local/bin/app1

ENTRYPOINT ["/usr/local/bin/app1"]
