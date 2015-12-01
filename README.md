Pico
====

[![License](https://img.shields.io/github/license/picocms/Pico.svg)](https://github.com/picocms/Pico/blob/master/LICENSE)
[![Version](https://img.shields.io/github/release/picocms/Pico.svg)](https://github.com/picocms/Pico/releases/latest)
[![Build Status](https://img.shields.io/travis/picocms/Pico.svg)](https://travis-ci.org/picocms/Pico)
[![Scrutinizer Code Quality](https://img.shields.io/scrutinizer/g/theshka/pico.svg)](https://scrutinizer-ci.com/g/theshka/Pico/?branch=master)
[![Tweet Button](https://cloud.githubusercontent.com/assets/640217/11483728/b0842918-976f-11e5-9185-d53261b3125b.png)](https://twitter.com/intent/tweet?text=Pico+is+a+stupidly+simple%2C+blazing+fast%2C+flat+file+CMS.+Visit+http%3A%2F%2Fpicocms.org+and+downlaod+%23picocms+today%21+via+%40gitpicocms&amp;related=gitpicocms)

Pico is a stupidly simple, blazing fast, flat file CMS. See http://picocms.org/ for more info.

Screenshot
-------

![Pico Screenshot](https://cloud.githubusercontent.com/assets/640217/11488304/1b17b388-978b-11e5-9827-532d14a79f2e.gif)

Table of Contents
-------
* [Pico](#pico)
* [Install](#install)
    * [Pre-Bundled Release](#using-a-pre-bundled-release---for-users)
    * [Using Composer](#using-composer---for-developers)
* [Upgrade](#upgrade)
* [Run](#run)
* [Config](#config)
* [Getting Help](#getting-help)
    * [...as a user](#-as-a-user)
    * [...as a developer](#-as-a-developer)
    * [... still need help?](#-still-need-help-with-pico)
* [Contributing](#contributing)

Install
-------

You can install Pico either using a pre-bundled release or with composer. Pico is also available on [Packagist.org][] and may be included in other projects via `composer require picocms/pico`. Pico requires PHP 5.3+

### Using a pre-bundled release - for users

1. [Download the latest Pico release][LatestRelease]

2. Upload all files to the `httpdocs` directory (e.g. `/var/www/html`) of your server.

### Using Composer - for developers

1. Open a shell and navigate to the desired install directory of Pico within the `httpdocs` directory (e.g. `/var/www/html`) of your server. You can now clone Pico's Git repository as follows:
    ```shell
    $ git clone https://github.com/picocms/Pico.git .
    ```
    > Please note that this gives you the current development version of Pico, what is likely *unstable* and *not ready for production use*!

2. Download [composer][] and run it with the `install` option:
    ```shell
    $ curl -sS https://getcomposer.org/installer | php
    $ php composer.phar install
    ```

[^ toc][]

Upgrade
-------

Upgrading Pico is very easy: You just have to replace all of Pico's files - that's it! Nevertheless you should *always* create a backup of your Pico installation before upgrading.

Pico follows [Semantic Versioning 2.0][SemVer] and uses version numbers like `MAJOR`.`MINOR`.`PATCH`. When we update...

- the `PATCH` version (e.g. `1.0.0` to `1.0.1`), we made backwards-compatible bug fixes. It's then sufficient to extract [Pico's latest release][LatestRelease] to your existing installation directory and overwriting all files. Alternatively you can either use the [*source code* of Pico's latest release][LatestRelease] or pull from Pico's Git repository, but are then required to update Pico's [composer][] dependencies manually by running `php composer.phar update`.

- the `MINOR` version (e.g. `1.0` to `1.1`), we added functionality in a backwards-compatible manner, but anyway recommend you to "install" Pico newly. Backup all of your files, empty your installation directory and install Pico as elucidated above. You can then copy your `config/config.php` and `content` directory without any change. If applicable, you can also copy the folder of your custom theme within the `themes` directory. Provided that you're using plugins, also copy all of your plugins from the `plugins` directory.

- the `MAJOR` version (e.g. `1.0` to `2.0`), we made incompatible API changes. We will then provide a appropriate upgrade tutorial.

Upgrading Pico 0.8 or 0.9 to Pico 1.0 is a special case. The new `PicoDeprecated` plugin ensures backwards compatibility, so you basically can follow the above upgrade instructions as if we updated the `MINOR` version. However, we recommend you to take some further steps to confine the necessity of `PicoDeprecated` as far as possible. For more information about what has changed with Pico 1.0 and a step-by-step upgrade tutorial, please refer to the [upgrade page of our website][HelpUpgrade].

[^ toc][]

Run
---

You have nothing to consider specially, simply navigate to your Pico install using your favorite web browser. Pico's default contents will explain how to use your brand new, stupidly simple, blazing fast, flat file CMS.

### You don't have a web server?
No worries! Starting with PHP 5.4 the easiest way to get started using Pico is with [PHP's built-in web server][PHPServer].

1. Navigate to Pico's installation directory using a shell.

2. Start PHPs built-in web server:
    ```shell
    $ php -S 127.0.0.1:8080
    ```
3. Access Pico from http://localhost:8080.

    > Please note that PHPs built-in web server is for *development* and *testing* purposes *only!*

[^ toc][]

Config
---
Once Pico is installed, you will need to copy your sites config file from `config/config.php.template` to `config/config.php`. The most important config items to set are `$config['timezone']`, `$config['base_url']`, and `$config['site_title']`

[^ toc][]

Getting Help
------------

### ... as a user
If you want to get started using Pico, please refer to our [user docs][HelpUserDocs]. Please read the [upgrade notes][HelpUpgrade] if you want to upgrade from Pico 0.8 or 0.9 to Pico 1.0. You can find officially supported plugins and themes on [our website][OfficialPlugins]. A greater choice of third-party plugins and themes can be found in our [Wiki][] on the [plugins][WikiPlugins] or [themes][WikiThemes] pages respectively. If you want to create your own plugin or theme, please refer to the "Getting Help as a developer" section below.

### ... as a developer
If you're a developer, please refer to the "Contributing" section below and our [contribution guidelines][ContributionGuidelines]. To get you started with creating a plugin or theme, please read the [dev docs on our website][HelpDevDocs].

### ... still need help with Pico?
When the docs can't answer your question or when you're experiencing problems with Pico, please don't hesitate to create a new [Issue][Issues] on GitHub. Concerning problems with plugins or themes, please refer to the website of the developer of this plugin or theme.

> **Before creating a new Issue,** please make sure the problem wasn't reported yet using [GitHubs search engine][IssuesSearch]. Please describe your issue as clear as possible and always include steps to reproduce the problem.

[^ toc][]

Contributing
------------

<!--flippa verify-->
[![I Love Open Source](http://www.iloveopensource.io/images/logo-lightbg.png)](http://www.iloveopensource.io/projects/524c55dcca7964c617000756)

You want to contribute to Pico? We really appreciate that! You can help make Pico better by [contributing code][PullRequests] or [reporting issues][Issues], but please take note of our [contribution guidelines][ContributionGuidelines]. In general you can contribute in three different areas:

1. Plugins & Themes: You're a plugin developer or theme designer? We love you guys! You can find tons of information about how to develop plugins and themes at http://picocms.org/plugin-dev.html. If you have created a plugin or theme, please add it to our [Wiki][], either on the [plugins][WikiPlugins] or [themes page][WikiThemes]. Doing so, we may select and promote your plugin or theme on [our website][OfficialPlugins] as officially supported!

2. Documentation: We always appreciate people improving our documentation. You can either improve the [inline user docs][EditInlineDocs] or the more extensive [user docs on our website][EditUserDocs]. You can also improve the [docs for plugin and theme developers][EditDevDocs]. Simply fork Pico from https://github.com/picocms/Pico, change the Markdown files and open a [pull request][PullRequests].

3. Pico's Core: The supreme discipline is to work on Pico's Core. Your contribution should help *every* Pico user to have a better experience with Pico. If this is the case, fork Pico from https://github.com/picocms/Pico and open a [pull request][PullRequests]. We look forward to your contribution!

[^ toc][]

[^ toc]: #table-of-contents
[Packagist.org]: http://packagist.org/packages/picocms/pico
[LatestRelease]: https://github.com/picocms/Pico/releases/latest
[composer]: https://getcomposer.org/
[SemVer]: http://semver.org
[PHPServer]: http://php.net/manual/en/features.commandline.webserver.php
[HelpUpgrade]: http://picocms.org/upgrade.html
[HelpUserDocs]: http://picocms.org/docs.html
[HelpDevDocs]: http://picocms.org/plugin-dev.html
[OfficialPlugins]: http://picocms.org/plugins.html
[Wiki]: https://github.com/picocms/Pico/wiki
[WikiPlugins]: https://github.com/picocms/Pico/wiki/Pico-Plugins
[WikiThemes]: https://github.com/picocms/Pico/wiki/Pico-Themes
[Issues]: https://github.com/picocms/Pico/issues
[IssuesSearch]: https://github.com/picocms/Pico/search?type=Issues
[PullRequests]: https://github.com/picocms/Pico/pulls
[ContributionGuidelines]: https://github.com/picocms/Pico/blob/master/CONTRIBUTING.md
[EditInlineDocs]: https://github.com/picocms/Pico/edit/master/content-sample/index.md
[EditUserDocs]: https://github.com/picocms/Pico/tree/gh-pages/_docs
[EditDevDocs]: https://github.com/picocms/Pico/tree/gh-pages/_plugin-dev
