.PHONY: build run stop clean test help

build:## Build
	go build -o awesome-api

run:## Run
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## Stop
	kill "$(pgrep awesome-api)" || true

clean: ## 
	pkill awesome-api || true
	rm -f awesome-api
	rm -f awesome-api.log


test:
	curl http://localhost:9999
	curl http://localhost:9999/health

help:           ## Show this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
