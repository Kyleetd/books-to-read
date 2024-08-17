# books-to-read API

## Steps to Run the Program Locally:

### 1. Allow Docker to access files in the working environment

- Download the repository locally.
- Click on the settings button on the top-right corner.
- Click "Resources".
- Click "File sharing".
- Click the "+" button and add the directory to the api/src folder.

### 2. Build the API Docker image:

```bash
docker build -t books-to-read-api .
```

### 3. Run the API Docker image:

#### Mac Example:

```bash
docker run -v /Users/kylee/Documents/Code/books-to-read/api/src:/src -p 8000:8000 books-to-read-api
```

#### Windows Example:

```bash
docker run -v D:\Users\Heather\Documents\Kylee\books-to-read\api\src:/src -p 8000:8000 books-to-read-api
```

#### What the API Docker container executes:

- Installs all the dependencies listed in the project's pyproject.toml, including uvicorn. (For manual setup outside of Docker, you would need to run `poetry install` and potentially `poetry add uvicorn` if not already included.)

  ```bash
  poetry install
  ```

- (Optional for manual setup) Activates the Poetry environment. This step is not needed when running the container, as the Dockerfile already sets up the environment, but you would need to do this manually if not using Docker.

  ```bash
  poetry shell
  ```

- Starts the FastAPI application

  ```bash
  uvicorn src.main:app
  ```
