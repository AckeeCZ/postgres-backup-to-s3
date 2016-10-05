# Backup container for PostgreSQL instances

This image provides a cron daemon that runs daily backups from postgres (clustered or single instance) to Amazon S3.

Following ENV variables must be specified:
 - `POSTGRES_HOST` contains the remote host (hostname or IP) connection string for pg_dump command line client option -h
 - `POSTGRES_PORT` contains the remote port number for pg_dump option -P
  - `postgresserver.domain.com:5432` in case of a single instance
 - `POSTGRES_USER` username used for connecting to the database
 - `POSTGRES_PASSWORD` password of user `POSTGRES_USER` who has access to all dbs
 - `S3_URL` contains address in S3 where to store backups
  - `bucket-name/directory`
 - `S3_ACCESS_KEY`
 - `S3_SECRET_KEY`
 - `CRON_SCHEDULE` cron schedule string, default '0 2 * * *'

