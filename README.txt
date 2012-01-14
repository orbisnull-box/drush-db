Tool to automatically create a backup of the database (using drush) in Drupal when you commit the changes

USE
install drush and drushdb in you PATH, chown +x to drush and drushdb

hgrc (.hg/hgrc):
[hooks]
pre-commit.sqldump=/usr/bin/drushdb dump && /usr/bin/hg add .system/sqldump/drupal-sql-dump.sql
post-update.sqlload=/usr/bin/drushdb load

