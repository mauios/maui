Maui
====

This repository contains manifest files for package development.
Manifest files describe the project structure and is used by git-repo
to fetch all the packages repositories.

How to use it
-------------

To prepare for cloning, perform the following procedure:

1. Create ~/bin/ subdirectory, include it in PATH, and then switch to it by executing the following commands:

```sh
mkdir ~/bin/
PATH=~/bin:$PATH
```

2. Download the repo script by executing the following command:

```sh
curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
```

3. Change the attribute of repo to make it executable by executing the command:

```sh
sudo chmod a+x ~/bin/repo
```

4. Create a new directory for Maui and then switch to it by executing the following commands:

```sh
mkdir ~/<Maui_Project>
cd ~/<Maui_Project>
```

## Clone latest sources

To clone the latest source of all projects over SSH, perform the following procedure:

1. Initialize the repository by executing one of the following commands, as appropriate.

For developer access:

```sh
repo init -u ssh://git@github.com/mauios/manifest.git
```

For read-only access:

```sh
repo init -u https://github.com/mauios/manifest.git
```

2. Synchronize the repository by executing the following command:

```sh
repo sync
```

## Get ready for development

repo doesn't create local branches for you, hence you end up with a
detached head that points to the last known good commit.

Before you start developing make sure you have local branches:

```sh
repo forall -c 'git checkout $REPO_RREV'
```
