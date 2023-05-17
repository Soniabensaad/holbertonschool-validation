## Prerequisites
This document provides instructions and information for building and maintaining the Awesome Inc. website. It includes requirements, the website's lifecycle, and command line usage.
Requirements
To build and run the website locally, the following software and dependencies are required:
Go-Hugo: Installation Guide
Make: Installation Guide
Lifecycle
The lifecycle of the Awesome Inc. website involves the following steps:
Installation: Clone the website repository from GitHub.
Configuration: Customize the website's configuration files according to your needs.
Content: Create or modify content pages, blog posts, and other website components.
Build: Use Hugo to build the static website files.
Deployment: Deploy the built website files to a hosting server or platform.
Command Line Usage
The following command line commands are available for managing the Awesome Inc. website:
## Lifecycle
make build: Builds the static website files using Hugo.
make check :should fail when one of the 2 following steps fails.
make validate :should validate the file ./dist/index.html by using the command 
line Holberton’s W3C Validator, but should not fail if the file is not valid.
make clean: Cleans the built website files and cache.
make help: Show help for all command.


Source Code Comments
The source code of the Awesome Inc. website contains comments to provide clarity and guidance. Here are some important comments to note:

In config.toml, modify the configuration options such as site title, description, and navigation menu.
Content files are located in the content/ directory. Each content page or blog post has a YAML front matter section at the top.
Layout files are located in the layouts/ directory. Customize the templates according to your design requirements.
Static assets like images, CSS, and JavaScript files can be placed in the static/ directory.
For more detailed information about the code structure and specific functionalities, please refer to the comments within the source code files.
