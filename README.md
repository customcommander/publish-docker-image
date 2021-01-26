# publish-docker-image

This template repository allows you to maintain your Docker image on GitHub and publish it to Docker Hub.

## How does it work?

This template enforces [semantic versioning][] by adopting the [Angular Commit Message Conventions][].

Why? So that we can fully automate the process of cutting GitHub releases:

1. Everytime you push to your default branch (which must be either `main` or `master`), a GitHub workflow will work out whether to cut a major, minor or patch release based on your commit messages since the previous release.

2. Once a GitHub release is cut, another GitHub workflow will start pushing that GitHub release to Docker Hub.

3. The `CHANGELOG.md` file is updated automatically.

## Setup Instructions

### Before you create a repository from this template

1. Make sure that the corresponding Docker Hub repository exists (or create it).
2. Make sure that the corresponding Docker Hub repository is **not** linked to a GitHub repository. (This is the default.)

### After you created a repository from this template

You *MUST* complete all these steps before you do anything else:

1. Go to your Docker Hub account and create a new [personal access token][gh-token] (and copy its value).

2. Go to your GitHub account and create a new [personal access token][dh-token] (and copy its value).

3. Create an [encrypted secret for your repository][gh-secret] named `GH_TOKEN` and set it to the token created in step 2.

4. Create an [encrypted secret for your repository][gh-secret] named `DOCKERHUB_TOKEN` and set it to the token created in step 1.

5. Create an [encrypted secret for your repository][gh-secret] named `DOCKERHUB_USERNAME` and set it to your Docker Hub username.

6. Replace the `IMAGE_TITLE` variable in `.github/workflows/publish.yml`.

### Finally

None of these are strictly required but it would make sense to have a look:

7.  Replace `Dockerfile` with your own content!

8.  Review and/or replace the `.dockerignore` file.

9.  Empty the `CHANGELOG.md` file.

10. Reset the version number in `package.json`.

11. Update the name, author and repository properties in `package.json` (but keep everything else unchanged).

12. The current NPM `build` script can be changed. It is invoked to test your Docker image before publishing it.

13. Replace this README with your own content ;)

[semantic versioning]: https://semver.org
[angular commit message conventions]: https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines
[gh-secret]: https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository
[gh-token]: https://docs.docker.com/docker-hub/access-tokens/
[dh-token]: https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token