---
layout: post
published: false
title: 'R, Travis and Github integration via GITHUB_PAT (personal access token)'
---
I started using RStudio BookDown to develop documentation for SciDB insight API.

The template has a `_deploy.sh` script that depends on setting of a Github PAT (personal access token). The script also uses the token to push to `gh_pages` branch of the repo (so that documentation built by travis is uploaded automatically). See code snippet below:

From [here](https://github.com/Paradigm4/insight-docs/blob/master/_deploy.sh)
```sh
git clone -b gh-pages https://${GITHUB_PAT}@github.com/${TRAVIS_REPO_SLUG}.git book-output
```

# How do you set GITHUB_PAT?

1. First create a personal access token at [Github developer settings](https://github.com/settings/tokens)

2. When you generate the token, make sure to add `repo` or `repo/public_repo` privilege (based on whether your repo is private or public). See more scope rules [here](https://developer.github.com/apps/building-oauth-apps/scopes-for-oauth-apps/)

3. Next, the token must be set as an environment variable named `GITHUB_PAT` in Travis CI settings for your repo 

- https://travis-ci.org/<organization-or-username>/<repo-name>/settings
- or in my case, https://travis-ci.org/Paradigm4/insight-docs/settings
