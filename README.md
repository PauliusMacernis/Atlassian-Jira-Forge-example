# About

This project contains a Forge app written in Javascript that displays some static and dynamic (incl. API call) content in a Jira issue panel.

## Resources

- [https://developer.atlassian.com/platform/forge/getting-started/](https://developer.atlassian.com/platform/forge/getting-started/) - getting started guide
- [https://developer.atlassian.com/platform/forge/build-a-hello-world-app-in-jira/](https://developer.atlassian.com/platform/forge/build-a-hello-world-app-in-jira/) - **a tutorial to be followed in the scope of this project**
- [developer.atlassian.com/platform/forge/](https://developer.atlassian.com/platform/forge) - documentation and tutorials explaining Forge.
- [https://developer.atlassian.com/platform/forge/set-up-forge/](https://developer.atlassian.com/platform/forge/set-up-forge/) - instructions to get set up
- [https://admin.atlassian.com/](https://admin.atlassian.com/) - Atlassian admin site

## Setup

- `nvm install --lts=Erbium` - use the version of nodejs on which forge runs (otherwise `forge` command may not be available at all).
- `forge login` - in case of API token secret, refer to [https://id.atlassian.com/manage-profile/security/api-tokens](https://id.atlassian.com/manage-profile/security/api-tokens)
- (`forge create` - in case we need to set up the new Atlassian site.)
- `forge lint --fix` - adds required scopes automatically to the manifest.yml file (e.g, read:jira-work). 
  - Whenever we change permissions, we must upgrade the app's installation, do the following to comply:
    - Stop the tunnel process
    - `forge deploy`
    - `forge install --upgrade`
    - `forge tunnel` (in case we don't want "hot reload", just use `forge deploy` instead)

### Notes
- Use the `forge deploy` command when you want to persist code changes.
- Use the `forge install` command when you want to install the app on a new site.
- Once the app is installed on a site, the site picks up the new app changes you deploy without needing to rerun the install command.

