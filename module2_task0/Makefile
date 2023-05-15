.PHONY: build run stop clean test help

help: ## Help
	@echo "Available targets:"
	@echo "  build    - Compile the source code to create the binary"
	@echo "  run      - Run the application in the background"
	@echo "  stop     - Stop the running application"
	@echo "  clean    - Stop the application, delete binary and log file"
	@echo "  test     - Test the application using curl"
	@echo "  help     - Display this help message"

build: ## Build
	go build -o awesome-api

run: ## Run
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## Stop
	-kill "$(pgrep awesome-api)" || true

clean: ## Clean
	-kill "$(pgrep awesome-api)" || true
	rm -f awesome-api
	rm -f awesome-api.log

test: ## Test
	@echo "Testing the application using curl..."
	@echo "Expected output:"
	@echo "  - Request to /: 404 Page Not Found"
	@echo "  - Request to /health: ALIVE"
	@echo ""
	@echo "Actual output:"
	@echo "  - Request to /:"
	@curl -s -o /dev/null -w "%{http_code} %{http_version}\n" http://localhost:9999/
	@echo ""
	@echo "  - Request to /health:"
	@curl -s http://localhost:9999/health
	@echo ""
	@echo "Please check the application logs (awesome-api.log) for additional details."

.DEFAULT_GOAL := help
