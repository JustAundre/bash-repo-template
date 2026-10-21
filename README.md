# Project Name

## Dependencies

Operating system must be *`Linux`

\* FreeBSD, MacOS nor any of their derivatives have been tested.

Required packages:

- `GNU Coreutils`
- `inotify-tools`
- `Bash 4.4+`

Required in-use Init. System

- `SystemD`

## Download

Use the following commands to clone any repository and its respective wiki.

```bash
# HTTPS Authentication
git clone --recurse-submodules https://github.com/user/repo.git
git clone --recurse-submodules https://github.com/user/repo.wiki.git

# SSH Key Authentication
git clone --recurse-submodules git@github.com:user/repo.git
git clone --recurse-submodules git@github.com:user/repo.wiki.git
```

Substitute "*user*" and "*repo*" with your target user and repository.

## Updating Submodules

```bash
git submodule update --init --recursive
```

## Quick Commands

> [!TIP]
>
> Combining these works and is recommended for many use cases during development/testing.

Running privileged scripts under userland (requires `fakeroot`):

```bash
fakeroot -- ./main.sh
```

Running a debugging session:

```bash
bash -x -- ./main.sh
```

Logging sessions (to file in CWD):

```bash
# Linux
script -a "exec-$(date +%s).log" -qc 'bash main.sh'

# BSD
script "exec-$(date +%s).log" bash main.sh
```
