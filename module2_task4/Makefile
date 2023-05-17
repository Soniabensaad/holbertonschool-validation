build: check
    @echo "Building the website..."
    @# Add the command to generate the website here

check: lint link-check

lint:
    @echo "Linting Markdown files..."
    @markdownlint README.md content/posts/

link-check:
    @echo "Checking links..."
    @markdown-link-check README.md content/posts/

clean:
    @echo "Cleaning the dist directory..."
    @rm -rf dist

validate:
    @echo "Validating HTML..."
    @python3 /opt/W3C-Validator/w3c_validator.py ./dist/index.html || true

post:
    @echo "Creating a new post..."
    @hugo new posts/$(POST_NAME).md
    @sed -i 's/title: .*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

help:
    @echo "Available targets:"
    @fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
