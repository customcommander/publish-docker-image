# publish-docker-image

A template repository for maintaining a Docker image on GitHub and automatically publishing it to Docker Hub.
## Caveat Emptor

After you created a repository from this template you are free to make any changes you fancy, but this template makes a few assumptions and has no intention to make any of these neither configurable or optional.

### There's only one Dockerfile

And that file is called `Dockerfile` and lives at the root of the repository.
### Pushing to the default branch triggers a release

As soon as your push commits to the default branch (either `main` or `master`) a GitHub workflow will start building your Docker image.

## Requirements

1. Create a [GitHub personal access token](https://github.com/settings/tokens) and copy its value.
2. In your repository go to `Settings > Secrets` click on `New repository secret` and create a secret named `GH_TOKEN` and set it to the token created in step 1.
3. Create a [Docker Hub personal access token](https://docs.docker.com/docker-hub/access-tokens/) and copy its value.
4. In your repository create a new secret (see step 2) named `DOCKERHUB_TOKEN` and set it to the token created in step 3.
5. In your repository create a new secret named `DOCKERHUB_USERNAME` and set it to your Docker Hub username.