# # Use an official Python runtime as a parent image
# FROM python:latest

# # Set the working directory
# WORKDIR /app

# # Install poetry for dependency management
# RUN curl -sSL https://install.python-poetry.org | python3 -

# # Add Poetry bin directory to PATH
# ENV PATH="/root/.local/bin:${PATH}"

# # Copy the rest of the application code
# COPY . ./

# # Install dependencies using Poetry
# RUN poetry install

# # Expose port 8000 to the outside world
# EXPOSE 8000

# # Run prestart script
# RUN poetry run bash ./prestart.sh

# # Run the application
# CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]


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

