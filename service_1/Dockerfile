# Stage 1: Build Go binary
FROM golang:1.24.4-alpine AS builder

WORKDIR /app

COPY . .

RUN go build -o service1

# Stage 2: Minimal runtime image
FROM alpine:latest

WORKDIR /app

COPY --from=builder /app/service1 .

RUN apk add --no-cache curl

EXPOSE 8001

CMD ["./service1"]