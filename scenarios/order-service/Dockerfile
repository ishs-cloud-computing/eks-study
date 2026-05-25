# syntax=docker/dockerfile:1.6
FROM golang:1.26-alpine AS builder
WORKDIR /workspace
COPY go.work ./
COPY shared/ shared/
COPY order-service/ order-service/
RUN go work edit -dropuse=./frontend && \
    go work edit -dropuse=./notification-service && \
    go work edit -dropuse=./payment-service && \
    go work edit -dropuse=./user-service
RUN cd order-service && \
    CGO_ENABLED=0 GOOS=linux go build -trimpath -ldflags="-s -w" -o /out/order-service .

FROM gcr.io/distroless/static-debian12:nonroot
COPY --from=builder /out/order-service /order-service
EXPOSE 8080 9090
USER nonroot:nonroot
ENTRYPOINT ["/order-service"]
