# Scaling Infrastructure as Code on Google Cloud Platform

This repository is the link hub for all demo repositories for the Google Next '24 talk "Scaling Infrastructure as Code: Proven Strategies and Productive Workflows" talk.  All repositories are used together to create a multi-project, multi-region, multi-runtime based infrastructure that hosts a real-time multiplayer game.

### [Live Demo](https://scalingiac.jcolemorrison.com/): https://scalingiac.jcolemorrison.com/

### Project Repositories

1. [Core Infrastructure](https://github.com/jcolemorrison/scalable-iac-gcp-core)

Deploys the core "user facing application", which in the case of this demo, is a real time multiplayer game server and client.

2. [Multiplayer Cloud Server](https://github.com/jcolemorrison/multiplayer-cloud-server)

A node.js + Colyseus based real-time game server application.

3. [Multiplayer Cloud Client](https://github.com/jcolemorrison/multiplayer-cloud-client)

A node.js + Phaser + Colyseus based game client that connects to the aforementioned game server

4. [Services Infrastructure](https://github.com/jcolemorrison/scalable-iac-gcp-services)

Deploys the supporting infrastructure for anscillary services used to support the core infrastructure.  Exists in a GCP project separate from the core infrastructure.

5. [Run Github App](https://github.com/jcolemorrison/terraform-google-run-github-app)

A Terraform module written for no code and HCP Waypoint point based workflows.  It creates a Google Cloud Run based service, github repository, and a full CI/CD pipeline that feeds back into Terraform Cloud.  Each service is set up with ready-to-go read only access into the Multiplayer Game's read-replica datastores.  Also includes testing.

6. [Run Github App Code Template](https://github.com/jcolemorrison/scalable-iac-gcp-node-app-tpl)

The templated developer codebase used in the aforementioned Run Github App repo.  Includes the relevant Github Action based CI/CD pipeline to build down code into a Docker Image, push to Artifact Registry, and trigger an infrastructure update in Terraform Cloud.

7. [Function Github App](https://github.com/jcolemorrison/terraform-google-function-github-app)

Another Terraform module written for no code and HCP Waypoint point based workflows.  It creates a Google Cloud Function based service, github repository, and a full CI/CD pipeline that feeds back into Terraform Cloud.  Each function is set up with ready-to-go read only access into the Multiplayer Game's read-replica datastores.  Also includes testing.

8. [Function Github App Code Template](https://github.com/jcolemorrison/scalable-iac-gcp-node-fn-tpl)

The templated developer codebase used in the aforementioned Function Github App repo.  Includes the relevant Github Action based CI/CD pipeline to build down code, deploy it to the relevant Google Cloud Storage bucket, and trigger an infrastructure update in Terraform Cloud.

9. [Sentinel Policies](https://github.com/jcolemorrison/scalable-iac-gcp-policies)

HashiCorp Sentinel Policies used for "Policy as Code" enforcement in Terraform Cloud.