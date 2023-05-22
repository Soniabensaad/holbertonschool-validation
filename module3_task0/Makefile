# Prerequisites
# ...

## Lifecycle

build:   ## Generate the website from the markdown and configuration files in the directory dist/
	go build
	hugo > /dev/null 2>&1
	make check

clean:    ## Cleanup the content of the directory dist/
	rm -rf ./dist/ awesome-api awesome-api.log coverage-unit.out coverage-integration.out
	make stop

post:     ## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
	hugo new posts/$(POST_NAME).md
	sed -i '/title:/c\title: "$(POST_TITLE)"' content/posts/$(POST_NAME).md

check: ## Checking markdown files
	markdownlint content/ && markdown-link-check content/posts/*.md

validate: ## Validates using Holberton tool
	python3 opt/W3C-Validator/w3c_validator.py dist/index.html || true

run: ## Runs the API and logs it
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## Stops the process with the specified PID number
	pkill awesome-api

lint: ## Checks for potential errors
	golangci-lint run

test: ## Executes all testing targets
    
	make unit-tests
	make integration-tests
	make validate

unit-tests: ## Runs unit-tests
	go test -v -short -coverprofile=coverage-unit.out

integration-tests: ## Runs integrated tests
	go test -v -coverprofile=coverage-integration.out

help: ## Shows help for all commands
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
