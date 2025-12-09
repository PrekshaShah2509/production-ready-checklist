# Database Checklist

Comprehensive database production readiness checklist covering schema, integrity, performance, backup, replication, and monitoring.

## Table of Contents

1. [Schema & Design](#schema--design)
2. [Indexing Strategy](#indexing-strategy)
3. [Data Integrity](#data-integrity)
4. [Backup & Recovery](#backup--recovery)
5. [Replication & Failover](#replication--failover)
6. [Performance Optimization](#performance-optimization)
7. [Security](#security)
8. [Monitoring](#monitoring)
9. [Documentation](#documentation)

---

## Schema & Design

### Schema Setup
- [ ] Database created
- [ ] Database character set appropriate (UTF-8)
- [ ] Database collation appropriate
- [ ] All tables created
- [ ] All columns defined correctly
- [ ] Primary keys defined
- [ ] Unique constraints defined
- [ ] Foreign key constraints defined
- [ ] NOT NULL constraints appropriate
- [ ] Default values set appropriately
- [ ] Check constraints defined
- [ ] Computed columns (if applicable)

### Data Types
- [ ] Appropriate data types chosen
- [ ] Column sizes appropriate
- [ ] Numeric precision correct
- [ ] Date/time types appropriate
- [ ] Text encoding correct
- [ ] Boolean fields use appropriate type
- [ ] Decimal/float trade-offs evaluated
- [ ] ENUM fields used appropriately

### Naming Conventions
- [ ] Table names follow convention
- [ ] Column names follow convention
- [ ] Index names follow convention
- [ ] Constraint names follow convention
- [ ] Stored procedure names follow convention
- [ ] Function names follow convention
- [ ] Reserved keywords not used
- [ ] Abbreviations consistent

### Schema Versioning
- [ ] Database schema version tracked
- [ ] Migration files version numbered
- [ ] Migration files ordered chronologically
- [ ] Migration rollback tested
- [ ] Schema change log maintained
- [ ] Deployment procedure documented

---

## Indexing Strategy

### Index Planning
- [ ] Query patterns analyzed
- [ ] Frequently searched columns identified
- [ ] Frequently joined columns identified
- [ ] Frequently sorted columns identified
- [ ] Index candidates documented
- [ ] Index maintenance cost considered
- [ ] Write operation impact evaluated

### Index Creation
- [ ] Single column indexes created
- [ ] Composite indexes created strategically
- [ ] Unique indexes on unique columns
- [ ] Index selectivity evaluated
- [ ] Index cardinality appropriate
- [ ] Partial indexes used (if applicable)
- [ ] Covering indexes used (if applicable)

### Index Performance
- [ ] Index usage monitored
- [ ] Unused indexes identified
- [ ] Duplicate indexes removed
- [ ] Index fragmentation measured
- [ ] Index rebuild scheduled
- [ ] Index statistics updated
- [ ] Slow query analysis using indexes

### Constraints vs. Indexes
- [ ] Unique constraints use indexes
- [ ] Foreign key constraints indexed
- [ ] Primary key indexed
- [ ] Partial indexes for filtered queries
- [ ] Index limitations understood

---

## Data Integrity

### Constraints
- [ ] Primary key constraint on all tables
- [ ] Foreign key relationships enforced
- [ ] Referential integrity enforced
- [ ] Cascading delete rules appropriate
- [ ] Cascading update rules appropriate
- [ ] Circular dependencies avoided
- [ ] Constraint names meaningful

### Data Validation
- [ ] Column NOT NULL constraints set
- [ ] Column default values validated
- [ ] Check constraints for valid ranges
- [ ] Data type constraints enforced
- [ ] Length constraints enforced
- [ ] Pattern constraints (regex, format)
- [ ] Business rule constraints

### Data Consistency
- [ ] Transactional consistency
- [ ] Cross-table consistency validated
- [ ] Denormalization consistency managed
- [ ] Derived data consistency
- [ ] Calculated fields consistency
- [ ] Data quality issues identified
- [ ] Data cleansing completed

### Testing
- [ ] Constraint violation testing
- [ ] Cascading delete testing
- [ ] Data type constraint testing
- [ ] Business rule validation testing
- [ ] Data migration integrity testing
- [ ] Concurrent modification testing

---

## Backup & Recovery

### Backup Strategy
- [ ] Backup frequency defined (daily, hourly, etc.)
- [ ] Backup retention policy defined
- [ ] Full backups scheduled
- [ ] Incremental backups configured
- [ ] Backup window defined (off-peak hours)
- [ ] Backup storage location secure
- [ ] Backup storage redundancy
- [ ] Backup encryption enabled

### Backup Automation
- [ ] Backup scripts automated
- [ ] Backup scheduling configured
- [ ] Backup success verified
- [ ] Backup failure alerts configured
- [ ] Backup logs maintained
- [ ] Backup email notifications sent
- [ ] Backup size monitored
- [ ] Backup growth tracked

### Backup Verification
- [ ] Backup integrity checked
- [ ] Backup can be read
- [ ] Backup size reasonable
- [ ] Backup timestamp correct
- [ ] Backup completeness verified
- [ ] Backup checksum validated
- [ ] Backup recovery tested

### Recovery Planning
- [ ] RTO (Recovery Time Objective) defined
- [ ] RPO (Recovery Point Objective) defined
- [ ] Recovery procedure documented
- [ ] Recovery procedure tested
- [ ] Recovery time measured
- [ ] Data loss acceptable defined
- [ ] Recovery team assigned
- [ ] Recovery communication plan

### Disaster Recovery
- [ ] Backup stored offsite
- [ ] Backup in separate geographic region
- [ ] Backup media tested
- [ ] Restore procedure documented
- [ ] Restore procedure tested monthly
- [ ] Restore time acceptable
- [ ] Backup accessibility verified
- [ ] Backup security verified

---

## Replication & Failover

### Replication Setup
- [ ] Replication type chosen (synchronous/asynchronous)
- [ ] Primary database configured
- [ ] Replica database configured
- [ ] Replication user created
- [ ] Replication user permissions minimal
- [ ] Replication connection secure
- [ ] Replication lag acceptable
- [ ] Replication monitoring enabled

### Replication Monitoring
- [ ] Replication lag monitored
- [ ] Replication status checked regularly
- [ ] Replication errors logged
- [ ] Replication alerts configured
- [ ] Replication consistency verified
- [ ] Replication performance acceptable
- [ ] Slave/replica thread healthy

### Failover Configuration
- [ ] Failover procedure documented
- [ ] Failover automated (if applicable)
- [ ] Failover testing scheduled
- [ ] Failover time acceptable
- [ ] Data loss on failover acceptable
- [ ] Failover communication plan
- [ ] Failover rollback plan
- [ ] Split-brain prevention configured

### Failover Testing
- [ ] Failover test completed
- [ ] Primary failure simulated
- [ ] Replica promotion tested
- [ ] Replica becomes new primary
- [ ] Failback procedure tested
- [ ] Data consistency after failover
- [ ] Application handles failover
- [ ] Failover time measured

---

## Performance Optimization

### Query Optimization
- [ ] Slow queries identified (using slow query log)
- [ ] Query execution plans reviewed (EXPLAIN)
- [ ] Query indexes optimized
- [ ] Query rewrites considered
- [ ] Query result sizes appropriate
- [ ] Query complexity reduced
- [ ] Joins optimized
- [ ] Subqueries optimized

### Database Tuning
- [ ] Database parameters tuned
- [ ] Connection pooling configured
- [ ] Buffer pool size optimized
- [ ] Cache configured
- [ ] Query cache used (if applicable)
- [ ] Sort buffer optimized
- [ ] Join buffer optimized
- [ ] Temp table space optimized

### Maintenance Tasks
- [ ] Index defragmentation scheduled
- [ ] Statistics updated regularly
- [ ] Query optimizer hints added (carefully)
- [ ] Stale data archived
- [ ] Log files rotated
- [ ] Temp files cleaned
- [ ] Unused objects removed
- [ ] Maintenance window scheduled

### Capacity Planning
- [ ] Database size growth tracked
- [ ] Space needed projected
- [ ] Expansion timeline planned
- [ ] Storage scaling strategy
- [ ] Sharding considered (if needed)
- [ ] Archiving strategy defined
- [ ] Data retention policy enforced

---

## Security

### Access Control
- [ ] Database user accounts created
- [ ] Users have minimal required privileges
- [ ] Root/admin account access restricted
- [ ] Application user has least privilege
- [ ] Backup user has minimal privilege
- [ ] Read-only users for reporting
- [ ] Default accounts disabled
- [ ] User passwords changed from defaults

### Network Security
- [ ] Database network access restricted
- [ ] Only app servers can connect
- [ ] Remote database access disabled
- [ ] Firewall rules configured
- [ ] Network encryption enabled (if remote)
- [ ] Database port not exposed publicly
- [ ] VPN required for remote access

### Encryption
- [ ] Data at rest encrypted (if sensitive data)
- [ ] Data in transit encrypted (TLS)
- [ ] Backups encrypted
- [ ] Encryption keys stored safely
- [ ] Encryption keys rotated
- [ ] Decryption authorized only
- [ ] Encrypted column searches optimized

### Audit & Logging
- [ ] Audit logging enabled
- [ ] User actions logged
- [ ] Schema changes logged
- [ ] Permission changes logged
- [ ] Access denied attempts logged
- [ ] Audit logs retained
- [ ] Audit log access restricted
- [ ] Audit log review scheduled

---

## Monitoring

### Performance Monitoring
- [ ] Database query time monitored
- [ ] Slow query log enabled
- [ ] Long-running queries identified
- [ ] Lock wait time monitored
- [ ] Connection usage monitored
- [ ] Memory usage monitored
- [ ] Disk I/O monitored
- [ ] CPU usage monitored

### Health Monitoring
- [ ] Database availability monitored
- [ ] Replication status monitored
- [ ] Backup success monitored
- [ ] Disk space monitored
- [ ] Memory availability monitored
- [ ] Connection pool status
- [ ] Table fragmentation monitored
- [ ] Index fragmentation monitored

### Alerting
- [ ] Database down alert
- [ ] Replication lag alert (if applicable)
- [ ] Disk space alert
- [ ] Memory usage alert
- [ ] Slow query alert
- [ ] Connection pool exhaustion alert
- [ ] Backup failure alert
- [ ] Long transaction alert

### Dashboards
- [ ] Database performance dashboard
- [ ] Capacity usage dashboard
- [ ] Backup status dashboard
- [ ] Replication status dashboard
- [ ] Query performance dashboard
- [ ] Real-time monitoring dashboard

---

## Documentation

### Schema Documentation
- [ ] Database purpose documented
- [ ] Table purposes documented
- [ ] Column meanings documented
- [ ] Constraints documented
- [ ] Relationships documented
- [ ] Data flow documented
- [ ] Business rules documented
- [ ] Special considerations noted

### Operational Documentation
- [ ] Backup procedure documented
- [ ] Recovery procedure documented
- [ ] Failover procedure documented
- [ ] Failback procedure documented
- [ ] Scaling procedure documented
- [ ] Upgrade procedure documented
- [ ] Maintenance procedure documented
- [ ] Troubleshooting guide

### Runbooks
- [ ] Database down runbook
- [ ] High disk usage runbook
- [ ] Slow queries runbook
- [ ] Replication lag runbook
- [ ] Backup failure runbook
- [ ] Performance degradation runbook
- [ ] Capacity issue runbook
- [ ] Data corruption runbook

### Access Documentation
- [ ] User accounts documented
- [ ] User privileges documented
- [ ] Password reset procedure
- [ ] Access request procedure
- [ ] Access audit schedule
- [ ] Access revocation procedure

---

## Production Readiness Checklist

- [ ] All schema elements created and tested
- [ ] Indexes created and performance validated
- [ ] Data integrity constraints in place
- [ ] Backup strategy verified working
- [ ] Backup restoration tested
- [ ] Recovery time acceptable
- [ ] Replication configured and tested
- [ ] Failover tested and documented
- [ ] Performance acceptable under expected load
- [ ] Security hardened
- [ ] Monitoring configured and alerting working
- [ ] Documentation complete
- [ ] Team trained on procedures
- [ ] Runbooks created
- [ ] On-call rotation assigned