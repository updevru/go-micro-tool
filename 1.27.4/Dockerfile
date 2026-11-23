FROM golang:1.27.4

ENV GOFLAGS="-buildvcs=false"
ENV GO_BUILD_FLAGS="-buildvcs=false"
ENV CGO_ENABLED=0
ENV GOTOOLCHAIN=local

## Protoc install
RUN apt-get update && apt install -y protobuf-compiler
# Версии генераторов из опубликованного образа 1.25.
RUN go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway@v2.27.3
RUN go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-openapiv2@v2.27.3
RUN go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.36.10
RUN go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.5.1
RUN go install github.com/yoheimuta/protolint/cmd/protoc-gen-protolint@v0.50.5

## Golangci-lint install
RUN go install github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.15.0

## Gotestsum install
RUN go install gotest.tools/gotestsum@v1.13.0
