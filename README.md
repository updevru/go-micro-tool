# Go Micro Tool

Docker image with pre-installed utilities for Go projects, particularly focused on gRPC development.

## Included Tools

- Go (version depends on the image tag)
- Protobuf compiler and related tools:
  - protoc-gen-grpc-gateway
  - protoc-gen-openapiv2
  - protoc-gen-go
  - protoc-gen-go-grpc
  - protoc-gen-protolint
- golangci-lint
- gotestsum

## Usage

```bash
docker pull updev/go-micro-tool:1.27.4
```

## Automated Builds

GitHub Actions builds and publishes images for changed version directories after a push to `main`. The Docker Hub tag matches the directory name. Pull requests that change `1.27.4/` or the workflow build and check the Go 1.27.4 image without publishing it.

### Required GitHub Secrets

To use this workflow, you need to set up the following secrets in your GitHub repository:

- `DOCKERHUB_USERNAME`: Your Docker Hub username
- `DOCKERHUB_TOKEN`: Your Docker Hub access token (not your password)

### Creating a New Release

For a new Go patch, add a directory named after the exact Go version and register its path in `.github/workflows/docker-publish.yml`. Use a fresh directory and tag to keep published images available for existing consumers.
