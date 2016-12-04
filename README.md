# instantWebDev

Instantly create a new drupal/wordpress LAMP dev environment for local sites/multisites

The goal is to give anyone with a Debian based linux machine an instant LAMP server with drush, wp-cli, and the ability to quickly add Drupal/Wordpress sites/multisites without any additional configuration. In addition to deploying local sites it also gives the user access to a few common administration tools.

## Prerequisites

- Debian/Ubuntu 16.04+

optional:

- Google Chrome
- Sublime Text

## Procedure

```
git clone https://github.com/hutchgrant/instantWebDev.git
cd ./instantWebDev
chmod +x ./instantWebDev
```

Run with:
```
./instantWebDev
```

you may also wish to make it executable from anywhere

```
sudo cp ./instantWebDev /usr/bin/
```

then simply:

```
instantWebDev
```

## Local Environment Setup

If you already have apache installed:

```
nano ./instantWebDev
```

Otherwise, run the script, it will detect apache missing and will install LAMP server, along with enabling mod_rewrite and mod_userdir
If drush or wp-cli are detected as missing, those will be installed as well.

Edit, save and exit:

```
# EDIT WITH YOUR MYSQL CREDENTIALS
db_user="root"
db_pass="password"
db_url="localhost"

# EDIT WITH YOUR PREFERRED DRUPAL/WORDPRESS DEFAULT ADMIN CREDENTIALS
Usr="admin"
Pass="password"
Email="admin@example.com"
```

## Remote Environment Setup

```
nano ./instantWebDev
```

Edit, save and exit:

```
arr[1,'site']="example.com"		    # Remote Site Name
arr[1,'ssh']="root@8.8.8.8"	            # SSH user@ipaddress
arr[1,'locMnt']="/home/user/sites/example"  # Local Folder for mounting your site
arr[1,'remMnt']="/var/www/example"          # Remote apache folder where the site is located

optional:

arr[1,'multisite']="example-multi.com"      # multisite directory name for drush to update, if no default site, otherwise delete line
```

## Basic Admin/Setup Menu Options:

```
------------------------------------------------
Instant Drupal/Wordpress Development Environment
---------------by hutchgrant--------------------
------------------------------------------------
1) Mount Site
2) Dismount Site
3) SSH site
4) Update All Remote
5) Update All Local
6) Add new local Drupal/Wordpress single/multi site
7) Exit
```

## Example Local Drupal Automated Installation

```
------------------------------------------------
Instant Drupal/Wordpress Development Environment
---------------by hutchgrant--------------------
------------------------------------------------
Which CMS do you want to use?
1) Drupal
2) Wordpress
1
What do you want to name the new site? (case sensitive, dont use spaces, caps or special chars)
mydrupalsite
Do you want to create a multisite(Drupal sites must be created as regular site first)? [y/n]
n
Project drupal (8.2.3) downloaded to /home/hutchgrant/public_html/mydrupalsite.                [success]
Project drupal contains:                                                                   [success]
 - 1 profile: standard
 - 14 themes: stark, twig, bartik, stable, classy, seven, testing_config_import, minimal,
testing_missing_dependencies, testing_multilingual, testing_multilingual_with_english,
drupal_system_listing_compatible_test, testing, testing_config_overrides
 - 70 modules: menu_link_content, update, migrate, ban, system, rdf, help, shortcut, book,
forum, search, tracker, toolbar, statistics, automated_cron, filter, editor,
config_translation, datetime_range, hal, locale, comment, entity_reference, language,
telephone, link, content_moderation, dblog, content_translation, field, field_ui, views_ui,
basic_auth, serialization, big_pipe, syslog, breakpoint, image, rest, block_content,
taxonomy, file, path, history, simpletest, aggregator, outside_in, block, config, ckeditor,
tour, menu_ui, inline_form_errors, node, user, views, datetime, migrate_drupal_ui,
dynamic_page_cache, quickedit, text, options, page_cache, contextual, responsive_image,
contact, block_place, migrate_drupal, color, action

You are about to create a /home/hutchgrant/public_html/mydrupalsite/sites/default/settings.php file and CREATE the 'mydrupalsite' database. Do you want to continue? (y/n): y
Starting Drupal installation. This takes a while. Consider using the --notify global       [ok]
option.
Installation complete.  User name: admin  User password: password                        [ok]
Congratulations, you installed Drupal!                                                     [status]
Cache rebuild complete.                                                                    [ok]
Created new window in existing browser session.
```

## License

instantWebDev is available under the [Apache 2.0 License](https://github.com/hutchgrant/instantWebDev/blob/master/LICENSE).

## Contributing

All contributions will be placed under the same Apache 2.0 license, contributers must agree to that license.
For more information see [contributing](https://github.com/hutchgrant/instantWebDev/blob/master/CONTRIBUTING.md).

## Creator

**Grant Hutchinson (hutchgrant)**




