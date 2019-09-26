FROM golang:1.10-alpine3.7 as build

WORKDIR /go/src/app1

COPY . .

RUN apk add git && \
    go get -d -v ./... && \
    go get -v -u github.com/gorilla/mux && \
    go build -o app1
    
FROM alpine

COPY --from=build /go/src/app1/app1 /

CMD ["./app1"]
