# Forge Hello World

This project contains a Forge app written in Javascript that displays `Hello World!` in a Jira issue panel. 

See [developer.atlassian.com/platform/forge/](https://developer.atlassian.com/platform/forge) for documentation and tutorials explaining Forge.

## Requirements

See [Set up Forge](https://developer.atlassian.com/platform/forge/set-up-forge/) for instructions to get set up.

## Quick start

- Modify your app by editing the `src/index.jsx` file.

- Build and deploy your app by running:
```
forge deploy
```

- Install your app in an Atlassian site by running:
```
forge install
```

- Develop your app by running `forge tunnel` to proxy invocations locally:
```
forge tunnel
```

### Notes
- Use the `forge deploy` command when you want to persist code changes.
- Use the `forge install` command when you want to install the app on a new site.
- Once the app is installed on a site, the site picks up the new app changes you deploy without needing to rerun the install command.

## Support

See [Get help](https://developer.atlassian.com/platform/forge/get-help/) for how to get help and provide feedback.


## etc.

- `nvm install --lts=Erbium` - use the version of nodejs on which forge runs (otherwise `forge` command may not be available at all).
- `forge lint --fix` - adds required scopes automatically to the manifest.yml file (e.g, read:jira-work). 
  - Whenever we change permissions, we must upgrade the app's installation, do the following to comply:
    - Stop the tunnel process
    - `forge deploy`
    - `forge install --upgrade`
    - `forge tunnel`