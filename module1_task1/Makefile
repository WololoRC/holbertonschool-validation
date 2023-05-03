build :
	@hugo

clean :
	@rm -r dist/*

post :
	@hugo new posts/$(POST_NAME).md
	@echo "---\n\
	title: \"$(POST_TITLE)\"\n\
	date: $$(date +'%Y-%m-%dT%H:%M:%S%z')\n\
	draft: true\n\
	---" > content/posts/$(POST_NAME).md
