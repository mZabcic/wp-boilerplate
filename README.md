



This repository contains all the tools you need to start building a modern WordPress theme, using all the latest front end development tools.



## It contains:

* Webpack4+ config and build
* ES Linting
* Style Linting
* PHP Error Check
* WPCS Style Guide
* BrowserSync
* PostCSS with plugins
* Build and Prebuild Bash Script
* .gitignore
* Sass files based on Infinum Handbook
* Precreated template files and helpers
* BEM menues
* Google rich snippets
* Object oriented codebase
* Namespacing
* Autoloader
* Project-specific wp-config
* Import / export scripts
* Project setup wizard
* ...

## Getting started

First you need to install WordPress locally, using any of the local development environment you prefer. You can use XAMPP, MAMP, WAMP, VVV, Docker or Laravel Valet. You'll also need to have [Node.js](https://nodejs.org/en/), [Composer](https://getcomposer.org/) and [WP-CLI](https://wp-cli.org/) installed.

To start, fork this repository to your own, and then clone it

```bash
git clone git@github.com:your-name/wp-boilerplate.git
```

If you are using VVV clone it in the `public_html` folder

```bash
git clone git@github.com:your-name/wp-boilerplate.git public_html
```

Run node script to setup your project and rename all files via wizard.
**Run this first and only once**

```bash
npm run rename
```

This will make changes to theme name, description, author, text domain, package, namespace, and constants (this is important when specifying environment variable).

https://github.com/dingo-d/browscap-vvv-utility


## Development Start

Builds assets in watch mode using Webpack.

```bash
npm start
```

## Browser sync

We are using BrowserSync to sync assets and enable easy cross-device testing.
It is tested on MAMP and Vagrant (VVV).

## Linting Assets (JS,SASS)

Lints JS and SASS using Webpack

```bash
npm run precommit
```

## Linting PHP ##

We are using [Infinum coding standards for WordPress](https://github.com/infinum/coding-standards-wp) to check php files.

To install it, you need to install [Composer](https://getcomposer.org/) first.

* Add this aliases to you bash config:

```bash
alias phpcs='vendor/bin/phpcs';
alias phpcbf='vendor/bin/phpcbf';
alias wpcs='phpcs --standard=vendor/infinum/coding-standards-wp/Infinum';
alias wpcbf='phpcbf --standard=vendor/infinum/coding-standards-wp/Infinum';
```
* Reload terminal

Checking theme for possible violations:

```bash
wpcs wp-content/themes/inf_theme
```

Autofix theme for minor violations:

```bash
wpcbf wp-content/themes/inf_theme
```

## Build

Build creates public folder in theme all the assets.

Check for errors js, css, php but not WP standards

```bash
bash bin/_prebuild.sh
```

Builds production ready assets

```bash
bash bin/_build.sh
```

## Import & Export

Details are located in the `README-project.md` file. Be sure to change the URL according to your project.

## Note

This theme uses OOP with namespaces and autoloader. We have also included `ci-exclude.txt` file, to point what files to exclude when deploying using continuous integration.

When you add new class in your theme, be sure to run

```bash
composer -o dump-autoload
```

to rebuild the composer's autoload class map. The reason why this isn't automatic is that we are folowing modified WordPress coding standards, and not PSR standards, so this has to be done manually.

## Recommended plugins

Below is the list of plugins that we've used when working with this boilerplate, so we can confirm that they are working

* Content:
  * Advanced Custom Fields PRO
  * Category Order and Taxonomy Terms Order
  * Post Duplicator
  * Nested Pages
  * TinyMCE Advanced
  * Regenerate Thumbnails

* Develop:
  * Debug Bar
  * Query Monitor

* Seo:
  * Yoast SEO
  * ACF Content Analysis for Yoast SEO

* Optimizations:
  * Autoptimize
  * Nginx Helper or WP Fastest Cache
  * WP-Optimize
  * Redirection
  * Transients Manager
  * Wordfence Security

* Multilanguage:
  * WPML Multilingual CMS
  * WPML String Translation
  * WPML Translation Management
  * Advanced Custom Fields Multilingual

* Other:
  * WordPress Importer
  * Mailgun

## Plugin

When working for a client it may be easier to add every additional functionality to the theme. Since you are using namespaces, this contains all the necessary logic in the theme. You can use plugins of course, but be careful how you are adding extra functionality, so that you don't run in the dependency hell.
If you need to expose certain functionality across the multisite we recommend that you create a plugin.

Plugins should be created using plugin boilerplate, with addition of namespaces and autoloader.

`https://wppb.me/`

## Credits

Infinum WordPress Boilerplate is maintained and sponsored by
[Infinum](https://www.infinum.co).

<img src="https://infinum.co/infinum.png" width="264">

## License

Infinum WordPress Boilerplate is Copyright ©2018 Infinum. It is free software, and may be redistributed under the terms specified in the LICENSE file.
