# borgmatic-defaults

My defaults for borgmatic backup configuration. 

## Requirements

These defaults are designed for Linux-based systems. They might work on Macs as well.

You need to have installed:

- borg / borgbackup
- borgmatic

## Usage

### Clone the repo

As **root**, clone the repo into /etc/borgmatic-defaults

`git clone git@github.com:rolandu/borgmatic-defaults.git /etc/borgmatic-defaults/`

## Set up your config

`cp /etc/borgmatic-defaults/template.yaml /etc/borgmatic/`

## Create your config(s)

Create your configs within `/etc/borgmatic` (or anywhere else).

## Create repo

Example flow:

```
## Initialize the repo:
borgmatic --config /etc/borgmatic/your_config.yaml init --encryption repokey

## Store the key:
borgmatic --config /etc/borgmatic/your_config.yaml key export

## Try to do an initial backup:
borgmatic --config /etc/borgmatic/your_config.yaml create --verbosity 1 --list --stats
```

... and then you can go ahead and use borgmatic as you like.
