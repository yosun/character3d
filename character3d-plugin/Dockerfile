# Use the official Python base image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy the pyproject.toml file and install dependencies using Poetry
COPY pyproject.toml .
RUN pip install --no-cache-dir poetry && \
    poetry config virtualenvs.create false && \
    poetry install --no-dev --no-interaction --no-ansi

# Copy the rest of the application code
COPY . .

# Expose the port your application will run on (if necessary)
EXPOSE 8000

# Run the application
CMD ["python", "main.py"]
