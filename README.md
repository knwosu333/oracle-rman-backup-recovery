# Oracle RMAN Backup & Recovery

A hands-on Oracle DBA portfolio project demonstrating RMAN backup, validation, restore, and recovery workflows.

## Topics Demonstrated
- Full database backup
- Incremental level 0 and level 1 backups
- Archived redo log backup
- Backup validation
- Database restore and recovery
- Datafile recovery
- Point-in-time recovery concepts
- RMAN reporting and maintenance

## Structure
- `backup/` — full and incremental backup examples
- `recovery/` — restore and recovery runbooks
- `validation/` — backup/database validation
- `maintenance/` — crosscheck and expired backup cleanup
- `docs/` — scenario-based DBA procedures

## Important
These are portfolio/lab examples. Paths, retention policies, channel configuration, recovery requirements, and Oracle versions differ by environment. Test all recovery procedures in a non-production environment before production use. Never commit production credentials or confidential data.
