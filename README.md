# Atuin Server

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/johnbeynon/render-atuin)

Deploy an Atuin server to Render to sync your command line history - see https://atuin.sh/ for more details

> **Warning**
> This will provision paid services by default, a $7 web service and a $7 Postgres database

## Manual Installation - Using the public repo

1. From the Render dashboard, [NEW > Blueprint](https://dashboard.render.com/select-repo?type=blueprint)
2. Copy/Paste the URL of this repo into the 'Public Git Repo' field and submit
3. Give the Blueprint a name
4. Click Apply to create the services

## Manual Installation - Using a fork

> **Note**
> When you fork a repo make sure to use the New > Blueprint flow and not the 'Deploy to Render' option - without changes that would deploy the original repo and not the fork

1. [Fork](https://github.com/johnbeynon/render-atuin/fork) the repo to your own Github account
2. From the Render dashboard, create a new blueprint, [NEW > Blueprint](https://dashboard.render.com/select-repo?type=blueprint)
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

Toggle `ATUIN_OPEN_REGISTRATION` back to false to prevent unwanted registrations
