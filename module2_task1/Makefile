lint: ##Checks if code have no possible errors
	@golangci-lint run main.go

build: lint##Compile the source code of the application to a binary named awesome-api, The first build may takes some time.
	@hugo
	@go build -o awesome-api main.go

post: ## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
	@hugo new posts/$(POST_NAME).md
	@echo "---\
	title: '$(POST_TITLE)'\
	date: $(date +"%Y-%m-%dT%H:%M:%S%z")\
	---" > content/posts/$(POST_NAME).md

run: ##Run the application in background by executing the binary awesome-api, and write logs into a file named awesome-api.log.
	@./awesome-api >./awesome-api.log 2>&1 &

stop: ##Stop the application.
	@pkill awesome-api

clean: ##Stop the application. Delete the binary awesome-api and the log file awesome-api.log 
	@rm -r dist
	@rm awesome-api awesome-api.log

test: ##Tests ports 9999 and health
	curl http://localhost:9999
	curl http://localhost:9999/health

help: ## Show this help usage
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
