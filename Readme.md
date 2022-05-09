# Helm + Kubernetes

## Objective

This repository contains two separate Helm charts - one for installing Traefik as an ingress controller
and one for installing the default Helm example NGINX application. However, several configurations are missing
and several parts of the application have been compromised.

Your goal is to modify and fix this repository in such a way, that a simple bash script `test.sh` passes successfully.

In this test, a curl request is made to localhost port 32150 using host `www.example-domain.com`. With these parameters,
Traefik running in a local Kubernetes cluster must route the request to example NGINX application, which must respond
with an NGINX welcome page.

## Testing setup

- Traefik is installed using a Helm chart located inside `traefik/charts/`
- Traefik and NGINX application are installed using Helm 3
- Both charts are installed to a locally running empty Kubernetes cluster using Helm CLI commands
- Kubernetes server version is 1.22

## Bonus task 1

Application has an autoscaler, which scales the service to at most 3 pods. Upscaling threshold must be
CPU usage `100m`. Threshold must be easily configurable.

## Bonus task 2

Traefik and application are installed to separate namespaces. Traefik by default cannot access the application,
but is granted access explicitly. The way used for access management is a free choice.
