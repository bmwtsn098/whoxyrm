FROM golang:1.18 as builder

ADD . /whoxyrm
WORKDIR /whoxyrm
RUN go mod init github.com/milindpurswani/whoxyrm
RUN go build

# Package Stage
FROM debian:bookworm-slim
ENV WHOXY_API_KEY "mayhem_fuzz"
COPY --from=builder /whoxyrm/whoxyrm /
