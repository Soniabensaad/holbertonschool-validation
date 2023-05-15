.PHONY: build run stop clean test help

help:## help
	@echo "Available targets:"
	@echo "  build    - Compile the source code to create the binary"
	@echo "  run      - Run the application in the background"
	@echo "  stop     - Stop the running application"
	@echo "  clean    - Stop the application, delete binary and log file"
	@echo "  test     - Test the application using curl"
	@echo "  help     - Display this help message"

build:## Build
	go build -o awesome-api

run:## Run
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## Stop
	kill "$(pgrep awesome-api)" || true

clean: ## clean
	kill "$(pgrep awesome-api)" || true
	rm -f awesome-api
	rm -f awesome-api.log


test:
	@curl http://localhost:9999
	@curl http://localhost:9999/health
