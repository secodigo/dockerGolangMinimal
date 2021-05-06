FROM golang:1.12.0-alpine3.9 as builder

RUN mkdir /app

ADD . /app

WORKDIR /app

RUN go build -o /go/bin/codeeducation

FROM scratch

COPY --from=builder /go/bin/codeeducation /go/bin/codeeducation

ENTRYPOINT [ "/go/bin/codeeducation" ]

CMD ["bash"]