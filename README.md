# Atuin Server

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/johnbeynon/render-atuin)

Deploy an Atuin server to Render to sync your command line history - see https://atuin.sh/ for more details

> :warning: **This will provision paid services by default**: $7 web service and a $7 Postres database

## Manual Installation

1. From the Render dashboard, NEW > Blueprint
2. Copy/Paste the URL of this repo into the 'Public Git Repo' field and submit
3. Give the Blueprint a name
4. Click Apply to create the services

## Client Configuration

A local Atuin client needs to be configured to point at the deployed Atuin instance, edit the [sync_address](https://atuin.sh/docs/config/#sync_address) property of `~/.config/atuin/config.toml` and set it to the Render service address. Ensure to uncomment the line.

## Usage

The `ATUIN_OPEN_REGISTRATION` environment variable controls whether the service will accept new registrations. To allow registration it needs to be set to `TRUE`.

Register with the server with:

```
$ atuin register -u <username> -e <email> -p <password>
```

and then force a sync with:

```
$ atuin sync
```
