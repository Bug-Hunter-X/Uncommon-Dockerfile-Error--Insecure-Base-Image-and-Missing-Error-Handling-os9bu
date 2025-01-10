# Uncommon Dockerfile Error: Insecure Base Image and Missing Error Handling

This repository demonstrates a common but often overlooked error in Dockerfiles: using an insecure base image (`ubuntu:latest`) and lacking robust error handling during package installation.

## Bug
The original `Dockerfile` uses `ubuntu:latest`, which is a moving target.  Updates to the base image can break your container. Additionally, it doesn't handle potential errors (like failing to install packages). 

## Solution
The solution includes:
* Using a specific, more secure, version of Ubuntu.
* Using a non-root user for increased security.
* Adding error handling to the `apt-get` and `pip3` commands.
* Using a `.dockerignore` file to prevent unnecessary files from being included in the image.