FROM golang:1.14

ENV APP_ENV dev

WORKDIR /go/src/st-compiler
COPY . .

RUN  go get -u github.com/go-errors/errors && \
    go get -u github.com/goccmack/gocc
    # go get -u github.com/go-sql-driver/mysql && \
    # https://www.bugsnag.com/blog/go-errors
    # go get -u github.com/goburrow/modbus && \
    # go get -u github.com/serhioromano/mysqlsync && \
    # go get -u github.com/gomodule/redigo/redis && \
    # go get -u github.com/sirupsen/logrus

RUN go get -d -v ./...
RUN go install -v ./...

VOLUME ["/var/log/icod"]

CMD ["./st"]
