build:## Create all the files needed to to deploy the web page on the 'dist' directory.
	@hugo

clean:## Delete all content on the 'dist' directory.
	@rm -r dist/*

post:## Create the '.md' files inside 'content/posts' with the attibutes neded. Atts: $POST_NAME, $POST_TITLE
	@hugo new posts/$(POST_NAME).md
	@echo "---\n\
	title: \"$(POST_TITLE)\"\n\
	date: $$(date +'%Y-%m-%dT%H:%M:%S%z')\n\
	draft: true\n\
	---" > content/posts/$(POST_NAME).md

help:## Show this help usage
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
