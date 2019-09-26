FROM golang:1.10-alpine3.7 as build

WORKDIR /go/src/app2

COPY . .

RUN go build -o app2

FROM alpine:3.7

COPY --from=build /go/src/app/app2 /usr/local/bin/app2

ENTRYPOINT ["/usr/local/bin/app2"]
