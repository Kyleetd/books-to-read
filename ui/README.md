# books-to-read UI

## Steps to Run the Program Locally:

### 1. Build the UI Docker image:

```bash
docker build -t books-to-read-ui .
```

### 2. Run the UI Docker image:

```bash
docker run -p 3000:3000 books-to-read-ui
```

#### What the UI Docker container executes:

```bash
npm install
```

```bash
npm run dev
```
