# Joom TUF docker

## VARS

| ⚠️ REQUIRED ⚠️ | VAR | DEFAULT | COMMENT |
| ⚠️ | GIT_BRANCH_NAME    |          | The Branch name to checkout in the Container |
|    | TUF_VERSION        | `v0.1.0` | The go-tuf version insalled |
| ⚠️ | ACCESS_TOKEN       |          | Github Access token with access to the `GIT_RUL` |
|    | GIT_URL            | <https://github.com/joomla/updates.git> | The Github Repo URL |
|    | GITHUB_CLI_VERSION | `2.6.0`  | The Github CLI Version to install |

## Setup

Build the Image

```bash
docker build -t joom-tuf:latest -f Dockerfile .
```

Run your commands directly against tuf.
Use `-e` in `docker run` to pass ENV variables.

```bash
docker run -e ACCESS_TOKEN=REDACTED_TOKEN -e GIT_BRANCH_NAME=main joom-tuf "help"
usage: tuf [-h|--help] [-d|--dir=<dir>] [--insecure-plaintext] <command> [<args>...]
```

## TODO

- Github access token, get repo from branch
  - $ACCESS_TOKEN
  - $GIR_BRANCH (quasi die version die gesignt wird)
  - optional parm $GIT_URL
- Github CLI create MR from sign
- local volume/folder for joomla packages to sing