# ub-ansible-deploy

## Required variables

### docker_git_repo_url
Url to git repo containing docker compose configuration

### docker_git_revision
Git revision for repo containing docker compose configuration

### env_variables
Environment variables that will be replaced in `.env`

### secret_env_variables
Environment variables that will replaced in `secrets.env`

## Optional variables

### deploy_directory
The directory where the docker repo will be checked out, default is "/apps"

### docker_directory
The directory where "docker_command" will be run, relative paths are evaluated relative to the docker compose repo directory, default is "./docker"

### docker_command
The command used to run docker-compose, relative paths are evalutaed relative to "docker_directory", default is "./docker-compose-release.sh"

## Optional templates

templates/sites/\<site-name\>.conf.j2
: Apache site configuration template to be written to /opt/gub-apache2/sites/\<site-name\>-\<host-alias\>.conf

See `example_playbook` directory for reference implementation.

templates/cron.d/<cron-file>.j2
: Cron file template to be written to /etc/cron.d/<cron-file>

## Variables

Extra variables available in templates are:

### repo_path

Path the deployed repo on remote server.

### repo_name

Name of the deployed repo.

### docker_directory_path

Path to docker directory on remote server.
