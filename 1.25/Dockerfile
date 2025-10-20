FROM golang:1.25

# Установка переменных окружения для решения проблемы с VCS
ENV GOFLAGS="-buildvcs=false"
ENV GO_BUILD_FLAGS="-buildvcs=false"
ENV CGO_ENABLED=0


## Protoc install
RUN apt-get update && apt install -y protobuf-compiler
RUN go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway@latest
RUN go install github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-openapiv2@latest
RUN go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
RUN go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
RUN go install github.com/yoheimuta/protolint/cmd/protoc-gen-protolint@v0.50.5

## Golangci-lint install
RUN go install github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.2.1

## Gotestsum install
RUN go install gotest.tools/gotestsum@latest
