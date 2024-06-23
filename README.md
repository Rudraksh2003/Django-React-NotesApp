<div align="center">
<img width="50%" src="http://i3.ytimg.com/vi/tYKRAXIio28/maxresdefault.jpg"/>

# Django & React Notes App
</div>




A simple notes application built with Django for the backend and React for the frontend.

## Table of Contents

- [Original Contributions by Dennis Ivy](#original-contributions-by-dennis-ivy)
- [Additional Contributions](#additional-contributions)
  - [Containerization](#containerization)
  - [CI/CD Pipeline with Jenkins](#cicd-pipeline-with-jenkins)
- [Cloning the Repository](#cloning-the-repository)
- [Setting Up the Virtual Environment](#setting-up-the-virtual-environment)
  - [Windows](#windows)
  - [Linux and Mac](#linux-and-mac)
- [Running the App](#running-the-app)
  - [Locally](#locally)
  - [Using Docker](#using-docker)
- [Setting Up CI/CD with Jenkins](#setting-up-cicd-with-jenkins)
  - [Prerequisites](#prerequisites)
  - [Pipeline Configuration](#pipeline-configuration)
- [Contributing](#contributing)
- [License](#license)

## Original Contributions by Dennis Ivy

Dennis Ivy originally developed the Django & React Notes App. His contributions include:

- Setting up the Django backend to handle the server-side logic and data processing.
- Creating the React frontend for a user-friendly interface to interact with the notes.
- Establishing the foundational project structure and initial configurations.

## Additional Contributions by Rudraksh @https://github.com/Rudraksh2003

### Containerization

To facilitate easier deployment and ensure consistency across different environments, the application has been containerized using Docker. This involves:

- Creating a `Dockerfile` to build the Docker image for the application.
- Providing instructions to build and run the application using Docker.

### CI/CD Pipeline with Jenkins

To automate the build, test, and deployment process, a CI/CD pipeline has been set up using Jenkins. This involves:

- Configuring a Jenkins pipeline to clone the repository, build the Docker image, and run the Docker container.
- Ensuring continuous integration and continuous deployment practices to streamline development and deployment workflows.

## Cloning the Repository

To get started, clone the repository using the command below:

```bash
git clone https://github.com/divanov11/Django-React-NotesApp.git
```

Move into the directory where we have the project files:

```bash
cd Django-React-NotesApp
```

## Setting Up the Virtual Environment

### Windows

Create a virtual environment:

```bash
virtualenv env
```

Activate the virtual environment:

```bash
.\env\Scripts\activate
```

### Linux and Mac

Create a virtual environment:

```bash
python -m venv env
```

Activate the virtual environment:

```bash
source env/bin/activate
```

## Running the App

### Locally

To run the Notes App locally, use the following command:

```bash
python manage.py runserver
```

Then, the development server will be started at [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

### Using Docker

#### Build the Docker Image

```bash
docker build -t my-django-app .
```

#### Run the Docker Container

```bash
docker run -p 8888:8000 my-django-app
```

Then, the development server will be started at [http://localhost:8888/#/](http://localhost:8888/#/)

## Setting Up CI/CD with Jenkins

### Prerequisites

- Jenkins installed and running
- Docker installed on Jenkins server
- GitHub repository access

### Pipeline Configuration

1. Open Jenkins and create a new pipeline job.

2. Configure your pipeline script 

3. Save the configuration and build the pipeline.

The Jenkins pipeline will clone the repository, build the Docker image, and run the Docker container.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or suggestions.

## License

This project is licensed under the MIT License.

---
