
# ML-Inz-example

This project contains two main components:
1. A Flask backend serving HTML, CSS, and JavaScript.
2. A machine learning service using the `nvidia/Llama3-ChatQA-1.5-8B` model to answer questions based on documents.

## Project Overview

### Flask Backend

The Flask backend serves the frontend application, which includes HTML, CSS, and JavaScript files. It provides the user interface where users can input their question and document, and view the generated answer.

### Machine Learning Service

The machine learning service utilizes the `nvidia/Llama3-ChatQA-1.5-8B` model. This service accepts a question and a document as input, processes them using the model, and returns an answer based on the content of the document.

## Features

- **Flask Backend**: Serves the frontend and handles user interactions.
- **ML Service**: Uses a state-of-the-art language model to provide answers based on the provided documents.
- **Docker Support**: Both components can be easily deployed using Docker and Docker Compose.
- **CORS Handling**: Ensures smooth interaction between the backend and the ML service.
- **Loading Indicator**: Shows a loading spinner while the ML model processes the input.

## Project Structure

```
my_project/
│
├── backend/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py
│   │   ├── templates/
│   │   │   └── index.html
│   │   ├── static/
│   │   │   ├── css/
│   │   │   │   └── style.css
│   │   │   └── js/
│   │   │       └── script.js
│   ├── __init__.py
│   ├── Dockerfile
│   ├── requirements.txt
│
├── ml_service/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py
│   │   ├── model.py
│   ├── __init__.py
│   ├── Dockerfile
│   ├── requirements.txt
│
├── tests/
│   ├── __init__.py
│   ├── test_backend.py
│   ├── test_ml_service.py
├── __init__.py
├── docker-compose.yml
├── setup.py
├── README.md
├── MANIFEST.in
└── pytest.ini
```

## Running the Project

### Using Docker Compose

To build and run the project with Docker Compose, use the following command:

```bash
docker-compose up --build
```

This command will build the Docker images for both the Flask backend and the ML service, and then start the containers.

### Backend

The Flask backend will be accessible at `http://localhost:8000`. It serves the frontend application where users can input their question and document.

### ML Service

The ML service will be accessible at `http://localhost:8001`. This service handles the processing of the question and document using the `nvidia/Llama3-ChatQA-1.5-8B` model and returns the answer.

## Usage

1. Open your browser and navigate to `http://localhost:8000`.
2. Enter your question in the provided input field.
3. Enter the document text in the provided textarea.
4. Click the "Generate" button.
5. Wait for the response to be generated and displayed below the form.

## Development

### Prerequisites

- Docker and Docker Compose
- Python 3.11 or higher

### Setting Up the Environment

1. Clone the repository:

```bash
git clone https://github.com/Appjey/ML-Inz-example.git
cd my_project
```

2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\ScriptsActivate`
```

3. Install the dependencies:

```bash
pip install -r backend/requirements.txt
pip install -r ml_service/requirements.txt
```

### Running Locally

To run the backend locally:

```bash
cd backend
python app/main.py
```

To run the ML service locally:

```bash
cd ml_service
python app/main.py
```

### Running Tests

To run the tests, use the following command:

```bash
pytest
```

## Contributing

If you would like to contribute, please open a pull request with your changes. Make sure to update the tests as appropriate.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
