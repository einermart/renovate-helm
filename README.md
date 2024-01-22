# renovate-helm

This repository deploys two applications using Helm Charts. 

- `awx-operator` uses the full URL to the private nexus repo.
- `traefik` chart uses helm repo [alias](https://helm.sh/docs/topics/charts/#:~:text=repository%3A%20(optional)%20The%20repository%20URL%20(%22https%3A//example.com/charts%22)%20or%20alias%20(%22%40repo%2Dname%22)) in the repository source.

## The Issue

- Renovate configuration file is setup to use [registryAliases](https://docs.renovatebot.com/configuration-options/#registryaliases). However, the configuration fails to create a PR on the `traefik` deployment because it cannot find a repository to query.
