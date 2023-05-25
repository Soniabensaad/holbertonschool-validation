# Use the official golang image as the base image
FROM golang:1.15.8-buster

# Install additional tools and dependencies
RUN apt-get update && apt-get install -y \
    go get -u github.com/golangci/golangci-lint/cmd/golangci-lint@v1.33.0
