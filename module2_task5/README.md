# Prerequisites

- Use the theme "ananke" for the website by following this Quickstart.
- If you are using the sandbox, do NOT install Hugo with the package manager. Download the correct executable or package file from their GitHub.
- Usage of Git Submodules is prohibited: there should be no file `.gitmodules`.
- The website title should be "Awesome Inc."
- The contents consist of a single blog post with the title "Welcome to Awesome Inc.", stored in a file named `welcome.md`.
- All of the website's source code is stored under a directory named `module1_task0`.
- The command line `hugo` version 0.84.0 must be used.
- The website is expected to be generated into the directory `module1_task0/dist/`.
- The directory `module1_task0/dist/` must not be committed (it should be absent from the repository).
- The Makefile must be present.

## Lifecycle

- `build`: Generate the website from the markdown and configuration files in the directory `dist/`.
- `check`: Check markdown files.
- `clean`: Clean up the content of the directory `dist/`.
- `post`: Create a new blog post using environment variables `POST_TITLE` and `POST_NAME`.
- `stop`: Kill the process with PID number.
- `run`: Run the API and log it.
- `lint`: Check for potential errors.
- `test`: Run all tests.
- `unit-tests`: Run unit tests.
- `integration-tests`: Run integrated tests.
- `validate`: Validate using the Holberton tool.
- `help`: Show help for all commands.
