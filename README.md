# ub-ansible-deploy

## Required variables

### git_repo_url
Url to git repo containing docker compose configuration

### git_revision
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
