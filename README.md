# Dockerfile Bug: Outdated Base Image and Uncleaned Packages

This repository demonstrates a common error in Dockerfiles: using an outdated base image and neglecting to clean up apt packages after installation.

The `Dockerfile` contains the buggy code, which uses `ubuntu:latest`, an outdated and insecure image.  The `apt-get` command installs necessary packages but fails to remove unnecessary files afterwards, resulting in a bloated image.

The `Dockerfile_fixed` demonstrates the corrected version, incorporating best practices like specifying a specific Ubuntu version, using `apt-get clean && apt-get autoremove` to remove unnecessary packages and temporary files, and maintaining a smaller image size.