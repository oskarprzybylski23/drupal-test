# Drupal-test

This repository contains a basic Drupal project to be run with Docker.

## Getting started

Run ``docker compose up -d``

6. Go to http://localhost:8081/ (or any port that was used for the PhpMyAdmin)
7. Create a new database in PhpMyAdmin
8. Go to http://localhost:8090/ to see Drupal installation window (or any port that was used for the Drupal container)
9. Installing Drupal:
    1. Click through selecting relevant options until **Set up database**
    2. Enter database name, username and password as set in previous steps
    3. In **Advanced Options** set Host to database container name (here **mysqldb**)
    4. Click **Save and continue**
10. Configure site:
    1. Complete the fields as relevant

If encounter problems during installation check file permissions for mount bind host. These can be modified e.g. 

```
chmod -R 777 drupal-test/web/modules drupal-test/web/themes drupal-test/web/sites
```
or:
```
chmod 666 ./web/sites/default/settings.php
chmod 777 ./web/sites/default
```

After installation, secure the permissions where relevant:
```
chmod 444 ./web/sites/default/settings.php
chmod 755 ./web/sites/default
```