## Prerequisites ##
- A shell terminal with bash, zsh or ksh, including the standard Unix toolset (ls, cd, etc.) with:
- GNU Make in version 3.81+
- Go Hugo v0.84.0 (very crucial for the theme that you’ll use).
- Theneme 'ananke' installed
- publishDir setted to: /dir

## Lifecycle ##
- “build”: Generate the website from the markdown and configuration files in the directory dist/.
- “clean”: Cleanup the content of the directory dist/
- “post”: Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.
