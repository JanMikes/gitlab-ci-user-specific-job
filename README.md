# Gitlab CI restrict job only for predefined users
Gitlab CI demo for job that should run only when specific user runs the pipeline.

This is to demonstrate a job, that will appear only if the pipelines was triggered by one of the predefined users.

[Check `.gitlab-ci.yml`](https://github.com/JanMikes/gitlab-ci-user-specific-job/blob/main/.gitlab-ci.yml)

This repository is [mirrored to Gitlab](https://gitlab.com/janmikes/gitlab-ci-user-specific-job/activity), so you can check the pipelines.

## How it works

Variables can be defined either directly in the `.gitlab-ci.yml` file or in CI/CD variables in settings to prevent overriding by developers.

*Be careful, there is no easy way to prevent developers from editing `.gitlab-ci.yml` file, to allow job to run even without permissions.*

### Demo 1
`$ALLOWED_USERNAME` variable can contain single username - there is `==` operator and if pipeline is triggered by this user, job will appear.

### Demo 2
`$ALLOWED_USERNAMES` variable can contain multiple usernames divided by `|` (it is [regular expression](https://docs.gitlab.com/ee/ci/jobs/job_control.html#cicd-variable-expressions)) - there is `=~` operator and if pipeline is triggered any of the users, job will appear.

### Demo 3
`$ALLOWED_USERNAMES` variable can contain multiple usernames. It is a little different from **Demo 2** in the way that this job will always appear, but if username is not allowed, the job will fail and not continue.

## Motivation

Restrict access to deploy job only for some users.

Goal is to replicate [Gitlab CI Protected Environments](https://docs.gitlab.com/ee/ci/environments/protected_environments.html), as this feature is for premium plan only - therefore not available for everyone.
