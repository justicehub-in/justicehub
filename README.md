<h1 align="center">
	<img width="343" src="https://github.com/justicehub-in/justicehub/blob/main/jh_logo.png?raw=true" alt="JusticeHub Logo">
</h1>

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](README.md)
[![Gitter](https://img.shields.io/badge/forum-%20discourse-e0462f.svg?style=flat-square)](https://forum.justicehub.in/)
[![Newsletter](https://img.shields.io/badge/newsletter-%20substack-blue.svg)](https://dataforjustice.substack.com/)
[![Docs: latest](https://img.shields.io/badge/docs-latest-brightgreen.svg?style=flat)](https://docs.justicehub.in/)

[JusticeHub](https://justicehub.in) empowers communities for data-driven justice by making legal and justice data open, accessible and actionable.

JusticeHub is open-source and is based on [CKAN](https://github.com/ckan/ckan), an open-source data management system that makes data accessible and widely used by many popular internet data portal

## Documentation

### How Justicehub is designed

Justicehub make use of open source tool called CKAN as DMS (Data Management System). Given how CKAN is progressing, currently we make use CKAN 2.8 as of now which make use of both pylons and Flask which lives side by side (more [info](https://docs.ckan.org/en/2.8/extensions/flask-migration.html)).

As for how to get started,
CKAN Installation can be found [here](https://github.com/justicehub-in/justicehub/wiki/How-to-setup-CKAN-on-Dev-server)

JusticeHub makes use of default tech stack which includes:

1. Python/Pylons Framework
2. Postgresql Database
3. Redis Cache
4. Solr Search Index

CKAN standalone doesn't solve all the problems and customization is still an issue which we try to solve. Some of the challenges which includes:

1. Theming 
2. Custom Authentication model
3. Data visualization like Table view
4. Moderation for datasets

Given how CKAN is structured, we try to overwrite it's logic by using plugins.

Hence for CKAN Customization, we make use of plugins, list of plugins which we created are:

|  Plugin Name  |  Description  |
| ------------- | ------------- |
| [ckanext-justicehub_theme](https://github.com/justicehub-in/ckanext-justicehub_theme/) | Custom templates and Styling |
| [ckanext-emailauth](https://github.com/justicehub-in/ckanext-emailauth)  | User Authentication and Email verification |
| [ckanext-moderation](https://github.com/justicehub-in/ckanext-moderation) | Dataset and Resources API + Moderation |
| [ckanext-tableview](https://github.com/justicehub-in/ckanext-tableview) | Tabular dataset view (CSV, XLSX etc) |

Since we don't want to reinvent the same well, there are plugins which needs to be installed for usage from other repositories as mentioned:


| Plugin Name  | Description |
| ------------- | ------------- |
| [ckanext-googleanalytics](https://github.com/ckan/ckanext-googleanalytics)  | Extension for Google Analytics |
| [ckanext-pages](https://github.com/ckan/ckanext-pages) | Add simple pages to CKAN  |
| [ckanext-datapusher](https://github.com/ckan/datapusher) | Make data from resource file available via CKAN's DataStore API |
| [ckanext-issues](https://github.com/ckan/ckanext-issues) | Report issues with dataset |
| [ckanext-validation](https://github.com/frictionlessdata/ckanext-validation) | Dataset validation |
| [ckanext-scheming](https://github.com/ckan/ckanext-scheming) | Modify schema of dataset by JSON or YAML file |
| [ckanext-composite](https://github.com/EnviDat/ckanext-composite) | Structured dataset metadata with single / multiple field |
| [ckanext-pdfview](https://github.com/ckan/ckanext-pdfview) | Views for PDF files |
| [ckanext-sitemap](https://github.com/kata-csc/ckanext-sitemap) | For generating sitemap.xml |
| [ckanext-contact](https://github.com/NaturalHistoryMuseum/ckanext-contact) | Adding popup contact forms to pages |
| [ckanext-downloadall](https://github.com/davidread/ckanext-downloadall) | Download all datasets in one click |


### Concepts from CKAN

CKAN Architecture allows us to write different modules which are:

1. Route  -> Allow you to overwrite any route (In pylons) or Blueprints (In Flask)
2. Views  -> Jinja templates or data views which is returned, you can overwrite existing views with another by plugins
3. API    -> You can also customize views and make them act as API to return JSON object, just like how we do for authentication with custom theme
4. Logic  -> Logic is core business idea for given modules, like auth model, actions which include create/update/delete of resource, user, or any entity
5. Models -> With plugins, you can also define your own tables / solr queries for different data storage like how we use for moderation plugin

Each plugins at the end is combination of RVLM (Route, Views, Logic, Models), which helps us to easily plug and play with different plugins.


## Contributions Best Practices

**Commits**
* Write clear meaningful git commit messages (Do read http://chris.beams.io/posts/git-commit/)
* Make sure your PR's description contains GitHub's special keyword references that automatically close the related issue when the PR is merged. (More info at https://github.com/blog/1506-closing-issues-via-pull-requests )
* When you're submitting a PR for a UI-related issue, it would be really awesome if you add a screenshot of your change. It makes it very easy for the reviewers and you'll also get reviews quicker.

**Feature Requests and Bug Reports**
* When you file a feature request or when you are submitting a bug report to the [issue tracker](https://github.com/justicehub-in/justicehub), make sure you add steps to reproduce it. Especially if that bug is some weird/rare one.

**Join the development**
* Before you join development, please set up the system on your local machine and go through the application completely. Explore and make sure you are comfortable with it
* Test the application on your machine and explore how datasets/resource/organizations interacting with each other.
* If you would like to work on an issue, drop in a comment at the issue. If it is already assigned to someone, but there is no sign of any work being done, please free to drop in a comment so that the issue can be assigned to you if the previous assignee has dropped it entirely.

## Code of Conduct

This project and everyone participating in it is governed by the [Justice Hub Code of Conduct](https://github.com/justicehub-in/Justice-Hub/blob/master/CODE_OF_CONDUCT.md).
By participating, you are expected to uphold this code. Please report unacceptable behavior to [info@justicehub.in](mailto:judiciary@civicdatalab.in).
