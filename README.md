# GT Reusable Docker workflows

This is repository is a collection of reusable workflow, dedicated to Docker, used by the GT's GitHub Actions jobs.

## Workflows

### `build-test-push-image.yml`

#### Features

- Build Docker images
- Support [container structure tests](https://github.com/GoogleContainerTools/container-structure-test)
- Push image to AWS ECR

#### Scenario

- Configure AWS Creds & ECR Registry
  - Used to define full `target` name and push image to AWS ECR
- `docker build` image with `latest` and `GIT_SHA` tags
- [Optionnal] test image with `container-structure-test` for both `latest` and `GIT_SHA` tags (requires config file)
- [Optionnal] push both `latest` and `GIT_SHA` tags for the built image
