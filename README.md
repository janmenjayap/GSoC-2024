# GSoC-2024
This repository contains the details of the project concerning Google Summer of Code 2024.

## Setting Up the Project Locally

To set up the development environment locally, follow these steps:

1. **Create a new conda environment:**
   ```bash
   conda create --name <conda_environment_name> python=3.12

2. **Install project dependencies:**
    ```bash
    pip install -r requirements.txt

## Building the Documentation Locally

To generate the HTML documentation locally:

1. Navigate to the `docs` directory:
   ```bash
   cd docs

2. Clean previous builds and generate the HTML files:
   ```bash
   make clean
   make html

3. Serve the documentation locally (still in the docs directory):
   ```bash
   python -m http.server <port_number> --directory _build/html

You can then access the documentation at `http://localhost:<port_number>` in your browser.

## Pushing Changes to the Repository

1. **Push Main Content (from root directory):**
   ```bash
   git add -A .
   git commit -m 'describe the changes here'
   git push origin main

2. **Push HTML Deployment (from `docs/_build/html` directory):**
   ```bash
   cd docs/_build/html
   git add -A . # at ./docs/_build/html
   git commit -m 'updated the webpage'
   git push origin gh-pages