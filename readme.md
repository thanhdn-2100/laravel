[![CircleCI](https://circleci.com/gh/euclid1990/laravel.svg?style=svg&circle-token=9b60b9bc13cffa647fa4ed7b4e70c07b0b7cba34)](https://circleci.com/gh/euclid1990/laravel)
[![codecov](https://codecov.io/gh/euclid1990/laravel/branch/master/graph/badge.svg?token=YEH69pYmyV)](https://codecov.io/gh/euclid1990/laravel)

# Laravel

## Stack

- Laravel 5.8.3

## TO DO List

- [x] Init Laravel
- [x] Init Docker development environment
- [x] Create base directory structure
- [x] Integrate coding convention checking tools ([PHP Codesniffer](https://github.com/squizlabs/PHP_CodeSniffer)/[EsLint](https://github.com/standard/eslint-config-standard)/[StyleLint](https://github.com/stylelint/stylelint-config-standard))
- [x] Continuous Integration configuration (Circle CI, ~~Sun CI~~)
- [x] Implement SSR Sign In | Sign Up | Sign Out + Unit Test
- [x] Implement SPA Sign In | Sign Up | Sign Out + Unit Test
- [x] Implement user's role base authorization + Unit Test
- [x] Implement exception handle and report to chat app (Chatwork, Slack)
- [x] Implement upload file + Unit Test
- [x] Implement resize/rotate/crop image + Unit Test
- [x] Implement read/write CSV + ~~Unit Test~~
- [ ] Implement read/write Excel + Unit Test
- [ ] Implement Logger + Unit Test

## Prerequisites

To install the development dependencies you will need:

- [Install Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/) & [Post-installation steps for Linux](https://docs.docker.com/install/linux/linux-postinstall/)
- [Install Docker compose](https://docs.docker.com/compose/install/)

## Development

```zsh
$ chmod a+x ./docker.sh
$ ./docker.sh start
```

- Web: https://localhost:8443 `[Basic Authenticate] user:web password:123456`
- PhpMyAdmin: https://localhost:8444
- API Documents: https://localhost:8445

## Build

- For re-build docker images and re-create containers
```zsh
$ ./docker.sh test-build
```
- Attach to a running container
```zsh
$ ./docker.sh exec {service_name}
```

## Testing

```zsh
$ ./docker.sh exec php
$ vendor/bin/phpunit
```

## Linting

- PHP code
```zsh
$ ./docker.sh exec php
### List coding standard rules
$ vendor/bin/phpcs -i
### Run phpcs check
$ vendor/bin/phpcs --extensions=php --standard=SunOS --encoding=utf-8 .
```
- Frontend code
```zsh
$ ./docker.sh exec node
### Run javascript check
$ yarn eslint.run
### Run css check
$ yarn stylelint.run
```

## Contribute

- Fork the repository and make changes on your fork in a feature branch.
- Commit messages must start with a capitalized and short summary.
- After every commit, make sure the test suite passes.
- Contributor sends pull request to release/develop branch, ask another contributor to check if possible.
- Don't push private keys, logs or any unnecessary files to git repository
- Merge when pull request got 2 OK from contributors and CI build is green.
- Merge develop to master to release final version.
