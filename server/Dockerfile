FROM golang:alpine as builder
WORKDIR /var/app
COPY main.go .
RUN go build -o app main.go

FROM alpine:latest  
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /var/app .
CMD ["./app"]  
