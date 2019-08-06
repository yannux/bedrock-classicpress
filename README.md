# Bedrock-ClassicPress

Bedrock-ClassicPress is the fork for [ClassicPress](https://github.com/ClassicPress/ClassicPress) of the modern WordPress statck by [roots.io/bedrock](https://roots.io/bedrock/) that helps you get started with the best development tools and project structure.

Much of the philosophy behind roots/Bedrock is inspired by the [Twelve-Factor App](http://12factor.net/) methodology including the [ClassicPress specific version](https://roots.io/twelve-factor-wordpress/).

## Features

* Better folder structure
* Dependency management with [Composer](https://getcomposer.org)
* Easy ClassicPress configuration with environment specific files
* Environment variables with [Dotenv](https://github.com/vlucas/phpdotenv)
* Autoloader for mu-plugins (use regular plugins as mu-plugins)
* Enhanced security (separated web root and secure passwords with [wp-password-bcrypt](https://github.com/roots/wp-password-bcrypt))

## Requirements

* PHP >= 7.1
* Composer - [Install](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)

## Installation

1. Create a new project:
    ```sh
    $ composer create-project yannux/bedrock
    ```

  This will setup the current main structure :
  ```
  your-project/
  |--config
  |--vendor
  |--web/
  |  |--app/
  |  |  |--/mu-plugins/
  |  |  |--/plugins/
  |  |  |--/themes/
  |  |  |--/uploads/
  |  |--wp/
  |  |--index.php
  |  |--wp-config.php
  |--.env.example
  |--.env
  |--composer.json
  |--composer.lock
  ```

2. Update environment variables in the `.env` file:
  * Database variables
    * `DB_NAME` - Database name
    * `DB_USER` - Database user
    * `DB_PASSWORD` - Database password
    * `DB_HOST` - Database host
    * Optionally, you can define `DATABASE_URL` for using a DSN instead of using the variables above (e.g. `mysql://user:password@127.0.0.1:3306/db_name`)
  * `WP_ENV` - Set to environment (`development`, `staging`, `production`)
  * `WP_HOME` - Full URL to ClassicPress home (https://example.com)
  * `WP_SITEURL` - Full URL to ClassicPress including subdirectory (https://example.com/wp)
  * `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT`
    * Generate with [wp-cli-dotenv-command](https://github.com/aaemnnosttv/wp-cli-dotenv-command)
    * Generate with [our ClassicPress salts generator](https://roots.io/salts.html)
3. Add theme(s) in `web/app/themes/` as you would for a normal ClassicPress site
4. Set the document root on your webserver to Bedrock's `web` folder: `/path/to/site/web/`
5. Access ClassicPress admin at `https://example.com/wp/wp-admin/`

## Documentation

Original Roots/Bedrock documentation is available at [https://roots.io/bedrock/docs/](https://roots.io/bedrock/docs/).
