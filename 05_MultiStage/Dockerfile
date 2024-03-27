FROM golang:alpine AS BUILDER
#최소로 동작하게

WORKDIR /go/src/app
COPY main.go .

RUN go mod init
RUN go build -o webserver .

CMD ["./webserver"]

#-------stage2---------
FROM alpine

WORKDIR /app
COPY --from=builder /go/src/app/ /app/

CMD ["./webserver"]