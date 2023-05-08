lint: ##Checks if code have no possible errors
	@golangci-lint run main.go

build: lint ##Compile the source code of the application to a binary named awesome-api, The first build may takes some time.
	@go build -o awesome-api main.go

run: awesome-api ##Run the application in background by executing the binary awesome-api, and write logs into a file named awesome-api.log.
	@./awesome-api >./awesome-api.log 2>&1 &

stop: awesome-api.log ##Stop the application.
	@pkill awesome-api

clean: awesome-api awesome-api.log ##Stop the application. Delete the binary awesome-api and the log file awesome-api.log 
	@pkill awesome-api
	@rm awesome-api awesome-api.log

test: awesome-api awesome-api.log ##Tests ports 9999 and health
	curl http://localhost:9999
	curl http://localhost:9999/health

help:## Show this help usage
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
