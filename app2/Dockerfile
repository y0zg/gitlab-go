FROM golang:1.10-alpine3.7 as build

WORKDIR /go/src/app2

COPY . .

RUN apk add git && \
    go get -d -v ./... && \
    go get -v -u github.com/gorilla/mux && \
    go build -o app2
    
FROM alpine

COPY --from=build /go/src/app2/app2 /

CMD ["./app1"]
