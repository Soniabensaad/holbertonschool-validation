# Base image
FROM golang:1.15.8-buster

# Install the required tools
RUN apt-get update && \
    apk add --no-cache --update curl gcc && \
    export GO111MODULE=on && \
    curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s -- -b $(go env GOPATH)/bin && \
    rm -rf /var/cache/apk/*

COPY . /usr/src/myapp

# Install markdownlint
# hadolint ignore=DL3016
RUN npm install -g markdownlint-cli

# Set the working directory in the container
WORKDIR /usr/src/myapp

