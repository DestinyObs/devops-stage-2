# Use an official Python runtime as a parent image
FROM python:latest

#install poetry
RUN pip install poetry

# Set the working directory
WORKDIR /application

#copy the rest of the application code
COPY pyproject.toml poetry.lock ./

# Install dependencies using Poetry
RUN poetry install --no-root

#copy the rest of the application code
COPY . .

ENV PYTHONPATH=/application

CMD poetry run bash ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0

