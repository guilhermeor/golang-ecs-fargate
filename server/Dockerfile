FROM golang:alpine as builder
WORKDIR /home/gui/go/src/server
RUN go version  
COPY main.go .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM alpine:latest  
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /home/gui/go/src/server .
CMD ["./app"]  