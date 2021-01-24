# publish-docker-image

A template repository for maintaining a Docker image on GitHub and automatically publishing it to Docker Hub.
## Caveat Emptor

After you created a repository from this template you are free to make any changes you fancy, but this template makes a few assumptions and has no intention to make any of these neither configurable or optional.

### There's only one Dockerfile

And that file is called `Dockerfile` and lives at the root of the repository.
### Pushing to the default branch triggers a release

As soon as your push commits to the default branch (either `main` or `master`) a GitHub workflow will start building your Docker image.