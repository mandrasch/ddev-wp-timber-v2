# DDEV + WordPress + Timber v2 + LaravelMix / Vite

- [DDEV](https://ddev.readthedocs.io/en/latest/)
- [Timber v2 (in development)](https://upstatement.com/timber/)
    - [Timber v2 starter theme (in development)](https://github.com/timber/starter-theme)


🚧 Work in progress, currently broken, see [issue #135](https://github.com/timber/starter-theme/issues/135) 🚧


See more experiments: https://my-ddev-lab.mandrasch.eu/

## Setup for local development

Clone this repo, then:

```bash
ddev start
ddev wp core download
# Finish installation in browser:
ddev launch

# Jump into DDEV container to work in sub-dir
ddev ssh
cd wp-content/themes/timber-starter-theme
composer install
exit

ddev wp theme activate timber-starter-theme/theme
ddev launch
```

## How was this created?

```bash
# https://ddev.readthedocs.io/en/stable/users/quickstart/#wp-cli

ddev config --project-type=wordpress
ddev start
ddev wp core download

# Finish install in browser
ddev launch

# https://timber.github.io/docs/v2
# jump into DDEV container to work with composer in sub-directory
ddev ssh
cd wp-content/themes/
composer create-project upstatement/timber-starter-theme:2.x-dev --no-dev
#TODO: why is --no-dev used in docs?
exit
# TODO: to be continued

ddev wp theme activate timber-starter-theme/theme
```

Added `.gitignore` afterwards to only track the child theme.