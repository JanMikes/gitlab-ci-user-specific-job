# Gitlab CI restrict job only for predefined users
Gitlab CI demo for job that should run only when specific user runs the pipeline.

This is to demonstrate a job, that will appear only if the pipelines was triggered by one of the predefined users.

[Check `.gitlab-ci.yml`](https://github.com/JanMikes/gitlab-ci-user-specific-job/blob/main/.gitlab-ci.yml)

This repository is [mirrored to Gitlab](https://gitlab.com/janmikes/gitlab-ci-user-specific-job/activity), so you can check the pipelines.

## Motivation

Restrict access to deploy job only for some users.

Goal is to replicate [Gitlab CI Protected Environments](https://docs.gitlab.com/ee/ci/environments/protected_environments.html), as this feature is for premium plan only - therefore not available for everyone.
