# Use an official Python runtime as the base image
FROM python:3.9-alpine

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Set the working directory in the container
WORKDIR /backend

# Install system dependencies
RUN apk add --no-cache curl

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 -

# Copy poetry.lock* in case it doesn't exist in the repo
COPY ./pyproject.toml ./poetry.lock* /backend/

# Install project dependencies
RUN poetry config virtualenvs.create false && poetry install --no-dev --no-interaction

# Copy the rest of the backend files
COPY . ./backend

# Run the prestart script
RUN poetry run sh ./prestart.sh

# Expose the port the app runs on
EXPOSE 8000

# Command to run the application
CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]