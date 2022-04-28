Hi !

The most common requests I see here are from users trying to setup a working self-hosted instance of Outline. Even though a few (very long) tutorials or (usually outdated) docker scripts exist It is still notoriously difficult get a fully working and well configured instance (Authentification without Slack, SSL certificates, working emails, working MinIO etc... ).

I am a member of the Yunohost project. It is a distribution based on Debian, which aims at making small personal server administration as simple as possible in order to democratize self-hosting. Part of the "magic" of Yunohost is the the fact that hundreds of popular self-hosted open source softwares are packaged as "apps" such that non tech users can install them with only one click.

I have been working since a few months now to bring Outline to Yunohost's catalog. It's now done and the "app" has been added. Installing Outline is now as simple as : 
* Installing Yunohost on a VPS or old computer at home
* Using the web admin interface to add and secure three subdomain names (if you don't have any, no worries, Yunohost will provide you with a ".noho.st" for free)
* Using the web admin interface to create one or more users
* Using the webadmin interface to install Outline

The package will automatically : 
1. Install and setup MinIO as the document manager
2. Install and setup Dex as an OIDC bridge to Yunohost's LDAP userbase
3. Download, build from sources and setup the latest version of Outline

All domains are secured with a Let's Encrypt certificate
Emails are working and sent through Yunohost's internal email server
Outline is built and running natively so there is no performance loss
You'll be able to update Outline with one click
You'll benefit from Yunohost's internal tools such as backup / restore mechanisms
You can of course install other apps to your Yunohost instance and benefit from a shared userbase (Nextcloud, Roundcube, Wallabag, Wordpress, Gitlab... Hundreds of them !)

Disclaimers : 
* Outline is built from sources, which is not the recommended way to run Outline
* Although the Yunohost package itself is under [AGPL-3.0 License](https://github.com/YunoHost-Apps/outline_ynh/blob/master/LICENSE), Outline's BUSL-1.1 licence is obviously still applying
* Yunohost has a full testing suite and quite a big community but Outline is still a very newly added app to the catalog, so there may be some bugs that we didn't find yet
* Yunohost is meant to be used for a personal or small organization server. Companies should be running their own infrastructures or using Outline's SaaS offer