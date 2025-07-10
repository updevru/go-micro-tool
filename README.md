# Go Micro Tool

Docker image with pre-installed utilities for Go projects, particularly focused on gRPC development.

## Included Tools

- Go 1.24
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
docker pull updev/go-micro-tool:latest
```

## Automated Builds

This repository uses GitHub Actions to automatically build and publish the Docker image to Docker Hub when a new version tag is created.

### GitHub Actions Workflow

The workflow is triggered when a tag starting with 'v' is pushed to the repository (e.g., v1.0.0). It builds the Docker image and pushes it to Docker Hub with both the version tag and the 'latest' tag.

### Required GitHub Secrets

To use this workflow, you need to set up the following secrets in your GitHub repository:

- `DOCKERHUB_USERNAME`: Your Docker Hub username
- `DOCKERHUB_TOKEN`: Your Docker Hub access token (not your password)

### Creating a New Release

To create a new release and trigger the workflow:

1. Tag your commit:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```

2. The GitHub Action will automatically build and publish the Docker image to Docker Hub.
