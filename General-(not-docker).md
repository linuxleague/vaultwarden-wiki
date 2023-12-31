## Backup

Things to include in your backup:

- The environment file used when starting Vaultwarden
- The `data` directory
- The Vaultwarden database
  - Use the database backup features of MariaDB/PostgreSQL/MySQL/SQLite to create a backup

Make sure you document the procedure and locations where backups are stored!

## Restore

- Install Vaultwarden
- Restore your database from backup
- Restore the environment file
- Restore your `data` directory to the correct location

## Platform specific

### FreeBSD port

| Item        | Location |
|-            |-         |
| Environment | `/usr/local/etc/rc.conf.d/vaultwarden` |
| Data        | `/usr/local/www/vaultwarden/data` |

### Database Backups

See e.g. [MariaDB - Backup and Restore Overview](https://mariadb.com/kb/en/backup-and-restore-overview/)
[SQLite](https://stackoverflow.com/questions/25675314/how-to-backup-sqlite-database)