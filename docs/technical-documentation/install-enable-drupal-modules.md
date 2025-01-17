## Downloading and Enabling Drupal Modules and Themes

Islandora can make use of majority of Drupal [modules](https://www.drupal.org/project/project_module) and [themes](https://www.drupal.org/project/project_theme). Common use cases have been documented in the [Islandora Cookbook](/documentation/user-documentation/extending/). There are several ways to download and install Drupal modules. Please refer to [this guide](https://www.drupal.org/docs/extending-drupal) on Drupal.org.

[Composer](https://www.drupal.org/docs/develop/using-composer/using-composer-to-install-drupal-and-manage-dependencies) is the recommended method to install and update drupal modules and themes in Islandora.
```shell
$ composer require "<vendor>/<package>:<version>"

# Example
$ composer require "islandora/islandora_defaults:1.0.0"
```

In the [Islandora playbook](https://github.com/Islandora-Devops/islandora-playbook), you can add a Drupal module's or theme's machine name to the `drupal_composer_dependencies` variable [here](https://github.com/Islandora-Devops/islandora-playbook/blob/dev/inventory/vagrant/group_vars/webserver/drupal.yml).
To enable the Drupal module or theme, add the module machine name to the `drupal_enable_modules` variable as well.

![alt text](../assets/install-enable-drupal-modules_drupal_composer_dependencies.png?raw=true "drupal_composer_dependencies Screenshot")

For modules that require additional steps, additional tasks may need to be added to the Ansible playbook. Re-provisioning your instance via Ansible will install the module.
