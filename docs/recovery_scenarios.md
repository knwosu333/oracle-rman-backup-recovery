# RMAN Recovery Scenarios

## Scenario 1 — Lost Datafile
1. Confirm the affected file using Oracle alert/log information and database views.
2. Verify usable RMAN backups and archived redo logs.
3. Offline the datafile when the scenario permits.
4. Restore the datafile with RMAN.
5. Recover it by applying required redo.
6. Bring the datafile online.
7. Validate application/database health.

## Scenario 2 — Database Restore
Before starting, determine the failure scope and recovery objective (RPO/RTO). Confirm backup availability and whether the control file, SPFILE, redo logs, and archived logs are available.

Typical workflow:
```
STARTUP MOUNT;
RESTORE DATABASE;
RECOVER DATABASE;
```

The final database open operation depends on the recovery scenario. Do not mechanically use `RESETLOGS` without understanding whether incomplete recovery or control-file recovery requires it.

## Scenario 3 — Point-in-Time Recovery
A DBA should first identify the desired recovery time/SCN and understand that changes after that recovery point can be lost. Use a tested backup, set the recovery target, restore, recover, validate, and then perform the appropriate open operation.

## Senior DBA Interview Discussion
Be prepared to explain:
- Restore vs. recovery
- Complete vs. incomplete recovery
- Level 0 vs. level 1 incremental backups
- Control file/SPFILE recovery
- Archived redo log requirements
- Recovery catalog vs. control-file repository
- Retention policy and obsolete vs. expired backups
- Why restore/recovery procedures must be tested regularly
