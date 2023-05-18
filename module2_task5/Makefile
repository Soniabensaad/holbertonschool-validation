# Prerequisites and environment variables...

# Lifecycle targets
.PHONY: build check clean post stop run lint test unit-tests integration-tests validate help

build: ## Generate the website from the markdown and configuration files in the directory dist/
	go build
	hugo > /dev/null 2>&1
	make check

check: ## Checking markdown files
	markdownlint content/ && markdown-link-check content/posts/*.md

clean: ## Cleanup the content of the directory dist/
	rm -rf ./dist/ awesome-api awesome-api.log coverage-units.out coverage-integrations.out
	make stop

post: ## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
	hugo new posts/$(POST_NAME).md
	sed -i '/title:/c\title: "$(POST_TITLE)"' content/posts/$(POST_NAME).md

stop: ## Kill the process with PID number
	pkill awesome-api

run: ## Run the API and log it
	./awesome-api > ./awesome-api.log 2>&1 &

lint: ## Check for potential errors
	golangci-lint run

test: ## Run all tests
	make unit-tests
	make integration-tests
	make validate

unit-tests: ## Run unit tests
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## Run integrated tests
	go test -v -coverprofile=coverage-integrations.out

validate: ## Validate using Holberton tool
	python3 opt/W3C-Validator/w3c_validator.py dist/index.html || true

help: ## Show this help usage
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
