#BUILD
FROM golang:1.18-alpine as build

COPY dispatcher.go .
RUN go build dispatcher.go

# RUN
FROM alpine:3.16.0

EXPOSE 80

COPY --from=build /go/dispatcher /
COPY static /static/

CMD ["/dispatcher"]