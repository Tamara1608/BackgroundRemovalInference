# Hunch Background Removal Inference Api
Welcome to our Image Background Removal API project! This repository serves as a resource for developers looking to integrate powerful background removal capabilities into their applications. Our API, built with FastAPI, provides a simple and efficient way to leverage an ONNX-based machine learning model for accurate foreground object extraction from images.

## Requirements
Before running the project make sure you have `python version 3` installed on your machine

## Installation & Setup
- Clone this repository using git
- Run the following commands:
    - macOS:
        ``` bash
        python3 -m venv venv
        source venv/bin/activate
        pip3 install -r requirements_mac.txt
        ```
    - windows (powerhshell):
        ``` powershell
        python -m venv venv
        .\venv\Scripts\Activate.ps1
        pip3 install -r requirements.txt
        ```
- these commands will create a new virtual environment, activate it and install all the necessary dependencies

## Usage
- before running the API, make sure the venv created earlier is active
- run the following command:
    - macOS:
        ```
        python3 app/main.py
        ```
    - windows (powershell):
        ```
        python app/main.py
        ```
- this will create a main process on `localhost:8000`, and one child process for each logical CPU on your machine
- if you wanna spawn just the main process, edit the last line in the `main.py` file to set the number of workers to 1:
    ``` python
    uvicorn.run("main:app", host="localhost", port=8000, reload=False, workers=1)
    ```
- to see the swagger docs, open `localhost:8000` in your browser
- inference is ran using the `/predict` endpoint. Enter a valid url to a jpeg image and the endpoint returns a `png` response image with no background