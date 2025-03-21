# Laradock Multi Version

Enable Laradock to run multiple PHP versions simultaneously

## Features

- Support running multiple PHP versions simultaneously
- No impact on Laradock updates (only modified one original Laradock file)

## Quick Start

### 1. Installation

Clone this project to your Laradock root directory:

```shell
git clone git@github.com:slowlyo/laradock-multi-version.git {your Laradock directory}/.laradock-multi-version
```

### 2. Configuration

Add the following configuration to your Laradock's `docker-compose.yml` file:

```yml
# Note: Must be placed at the first line of Laradock docker-compose.yml file
include:
  - .laradock-multi-version/docker-compose.yml
```

### 3. Start Services

Use docker compose command to start the required services:

```shell
# Example: Start PHP 7.4, PHP 8.0
# Execute in Laradock directory
docker compose up -d php-fpm-74 workspace-74 php-fpm-80 workspace-80 ...
```