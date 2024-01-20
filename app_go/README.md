 

## Running the application

```bash
go run main.go
```

## Usage


```bash
https://<APP_HOST>/?q=<REDIRECT_URL>
```

- For example, in order to get redirect to the google

```
https://localhost:8000/?q=https://google.com
```

### Other routes

- `/visits` - shows the total number of redirections performed by the application


## Development

### Testing

- Tests can be invoked with go test command
```bash
go test  ./... -v
```


## Docker

- How to build? 
    - `docker build -t app_go .`
- How to pull? 
    - `docker pull 0x22d1ab/app_go`
- How to run?  
    - `docker run --rm -it -p 8080:8080 --name app_go app_python 0x22d1ab/app_go `


## CI

### Trigger Events:
- Workflow name: "Build goredirector"
- Triggered on two events:
  - `push`: When changes are pushed to the repository (files within 'app_go/' or '.github/workflows/goredirector.yml').
  - `pull_request`: When pull requests are opened or updated (files within 'app_go/' or '.github/workflows/goredirector.yml').

### Jobs:
1. **lint**:
   - Lints Go code using golangci-lint.
   - Runs on Ubuntu 22.04 runner.
   - Steps:
     - Check out the code.
     - Setup Golang with caching based on 'go.mod' file.
     - Run golangci-lint to perform linting.

2. **test**:
   - Runs Go tests.
   - Matrix configuration for Ubuntu 22.04 and Ubuntu 20.04 runners.
   - Steps:
     - Check out the code.
     - Setup Golang with caching based on 'go.mod' file.
     - Run Go tests using the 'go test' command.

3. **snyk-check**:
   - Checks for vulnerable dependencies using Snyk.
   - Runs on Ubuntu 22.04 runner.
   - Steps:
     - Check out the code.
     - Run Snyk to check for vulnerable dependencies based on 'go.mod' file.

4. **build_push**:
   - Builds and pushes a Docker image to Docker Hub.
   - Runs on Ubuntu 22.04 runner.
   - Depends on 'lint', 'test', and 'snyk-check' jobs.
   - Steps:
     - Set up Docker Buildx for multi-platform image building.
     - Login to Docker Hub using GitHub secrets credentials.
     - Build and push a Docker image with 'latest' tag to Docker Hub.

**Note**:
- The 'test' job runs on two different Ubuntu versions using the `matrix` strategy.
- A section to run Snyk code tests is commented out, likely due to GitHub runner issues.
- Assumes variables like `secrets.DOCKERHUB_USERNAME` and `secrets.DOCKERHUB_TOKEN` are stored in GitHub secrets for Docker Hub authentication.

