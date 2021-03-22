# Amazon Database Backup 

- [Amazon Database Backup](#amazon-database-backup)
  - [Methods for RDS database backup](#methods-for-rds-database-backup)
    - [Using Automatic backups](#using-automatic-backups)
    - [Performing manual backups with snapshots](#performing-manual-backups-with-snapshots)
    - [Using the AWS Backup Service](#using-the-aws-backup-service)

## Methods for RDS database backup

### Using Automatic backups

- Uses a retention period, which must be set to at least 1 day
- The backup will not affect your storage I/O in case of multi-AZ instances
- RDS automatically stores backup on Amazon S3
- Snapshots are only supported for InnoDB storage engine and not MyISAM.

### Performing manual backups with snapshots


### Using the AWS Backup Service

