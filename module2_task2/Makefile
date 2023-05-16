build:	## Build:
	golangci-lint run
	go build

run:	## Run:
	./awesome-api >./awesome-api.log 2>&1 &

stop:  ## Stop:
	pkill awesome-api || true

clean: ## Clean:
	pkill awesome-api || true
	rm -rf awesome-api awesome-api.log

test:	## Test:
	curl http://localhost:9999
	curl http://localhost:9999/health

lint:	## Lint:
	golangci-lint run

unit-tests: ## unit-tests
        go test -v -short -coverprofile=coverage-units.out

help:	## Display this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
