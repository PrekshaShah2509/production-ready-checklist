# Post-Deployment Verification Guide

Comprehensive guide for verifying application health and performance after deployment.

## Table of Contents

1. [Immediate Checks (0-5 minutes)](#immediate-checks-0-5-minutes)
2. [Short-Term Monitoring (5-30 minutes)](#short-term-monitoring-5-30-minutes)
3. [Extended Monitoring (30 minutes - 24 hours)](#extended-monitoring-30-minutes---24-hours)
4. [Data Verification](#data-verification)
5. [Performance Validation](#performance-validation)
6. [Issue Detection](#issue-detection)
7. [Sign-Off Process](#sign-off-process)
8. [Documentation](#documentation)

---

## Immediate Checks (0-5 minutes)

### Application Health

**Basic Connectivity**
- [ ] Application URL responds (HTTP 200)
- [ ] Health check endpoint responds
- [ ] All server instances responding
- [ ] Load balancer routing correctly
- [ ] No connection refused errors
- [ ] DNS resolving correctly

**Service Status**
- [ ] Web server running
- [ ] Application process running
- [ ] Database connections established
- [ ] Cache server responding
- [ ] External services responding
- [ ] Message queue responding

**Application Startup**
- [ ] No startup errors in logs
- [ ] No connection pool errors
- [ ] No initialization failures
- [ ] All services initialized
- [ ] Configuration loaded correctly
- [ ] No missing dependencies

### Error Monitoring

**Error Rate**
- [ ] Error rate is baseline (0% increase acceptable)
- [ ] No spike in 5xx errors
- [ ] No spike in 4xx errors
- [ ] No cascade of errors
- [ ] Error log not growing exponentially
- [ ] No timeout errors

**Critical Errors**
- [ ] No database connection errors
- [ ] No null pointer exceptions
- [ ] No out of memory errors
- [ ] No permission denied errors
- [ ] No file not found errors
- [ ] No network timeouts

**Error Sources**
- [ ] Monitor application logs
- [ ] Monitor system logs
- [ ] Monitor database logs
- [ ] Monitor web server logs
- [ ] Check error tracking system
- [ ] Check alerting system

### Basic Functionality

**Homepage & Main Pages**
- [ ] Homepage loads
- [ ] Homepage renders correctly
- [ ] Navigation works
- [ ] Links working
- [ ] Images loading
- [ ] CSS/JS loading

**User Flows (if possible to test quickly)**
- [ ] Login flow works
- [ ] Home page accessible
- [ ] Main feature accessible
- [ ] No obvious UI breaks
- [ ] Responsive design works
- [ ] Dark mode works (if applicable)

---

## Short-Term Monitoring (5-30 minutes)

### Performance Metrics

**Response Time**
- [ ] Response time p50 normal (baseline ±10%)
- [ ] Response time p95 normal (baseline ±10%)
- [ ] Response time p99 normal (baseline ±10%)
- [ ] No spike in response times
- [ ] Response time trending stable
- [ ] Worst endpoint performance acceptable

**Throughput**
- [ ] Request rate normal for time of day
- [ ] Throughput stable
- [ ] No spike in request rate
- [ ] No unusual traffic patterns
- [ ] Rate limiting working correctly
- [ ] No queue backup

**Resource Usage**
- [ ] CPU usage normal (< 80%)
- [ ] Memory usage normal (< 85%)
- [ ] Disk I/O normal
- [ ] Network bandwidth normal
- [ ] No resource exhaustion
- [ ] No memory leaks

### Error Rate Monitoring

**Error Rate**
- [ ] Error rate stable
- [ ] Error rate same as pre-deployment
- [ ] No increasing trend
- [ ] 5xx error rate acceptable
- [ ] 4xx error rate acceptable
- [ ] No systematic errors

**Error Types**
- [ ] Timeout errors acceptable
- [ ] Database errors acceptable
- [ ] Network errors acceptable
- [ ] Permission errors acceptable
- [ ] Validation errors acceptable
- [ ] No unexpected error types

### User-Impacting Checks

**Critical Functionality**
- [ ] Login/authentication working
- [ ] Main workflow working
- [ ] Data operations working
- [ ] Search/filtering working
- [ ] Sorting working
- [ ] Pagination working
- [ ] File upload/download working (if applicable)

**Feature-Specific Checks**
- [ ] New features working (if deployed)
- [ ] Feature flags working (if used)
- [ ] A/B tests working (if used)
- [ ] Experiments working (if used)
- [ ] Known workflows working
- [ ] No regression in existing features

---

## Extended Monitoring (30 minutes - 24 hours)

### Database Health

**Connectivity**
- [ ] Database connections stable
- [ ] Connection pool not exhausted
- [ ] No connection failures
- [ ] Replication healthy (if applicable)
- [ ] Replica lag acceptable (if applicable)
- [ ] No database locks

**Performance**
- [ ] Query execution times normal
- [ ] Slow query count acceptable
- [ ] No query timeouts
- [ ] Index usage correct
- [ ] Table scan frequency acceptable
- [ ] No inefficient queries

**Data Integrity**
- [ ] No data corruption visible
- [ ] Data consistency verified (sampling)
- [ ] Transaction rollbacks acceptable
- [ ] Locks not held excessively
- [ ] Foreign key constraints intact
- [ ] Unique constraints intact

**Backup Status**
- [ ] Automated backup running
- [ ] Backup size reasonable
- [ ] Backup completion time acceptable
- [ ] Backup verification successful
- [ ] Backup alerts none
- [ ] Backup retention policy followed

### Infrastructure Health

**Server Health**
- [ ] All servers healthy
- [ ] CPU usage trending normal
- [ ] Memory usage trending normal
- [ ] Disk usage trending normal
- [ ] Network interfaces healthy
- [ ] No hardware errors
- [ ] No thermal issues

**Load Balancer Health**
- [ ] All backend servers available
- [ ] Health checks passing
- [ ] Traffic distribution even
- [ ] No sticky sessions issues
- [ ] Connection limits acceptable
- [ ] Failover working (if tested)

**Network Health**
- [ ] Network latency acceptable
- [ ] No packet loss
- [ ] Network capacity available
- [ ] DNS resolution working
- [ ] SSL/TLS certificates valid
- [ ] No network errors

### Cache Health

**Cache Status**
- [ ] Cache server responding
- [ ] Cache hit rate good
- [ ] Cache eviction rate acceptable
- [ ] Cache size reasonable
- [ ] Cache keys consistent
- [ ] No cache corruption

**Cache Invalidation**
- [ ] Cache clearing working
- [ ] Invalidation effective
- [ ] Stale data not served
- [ ] Cache TTLs appropriate
- [ ] Cache warming working

---

## Data Verification

### Data Consistency

**Sampling Verification**
- [ ] Random data sample verified
- [ ] Data looks correct
- [ ] Relationships intact
- [ ] Counts match expected
- [ ] No orphaned records
- [ ] No duplicate data

**Migration Verification** (if applicable)
- [ ] All data migrated
- [ ] No data loss
- [ ] Data format correct
- [ ] Data converted correctly
- [ ] Data validation passed
- [ ] Migration audit log checked

**Business Data**
- [ ] Critical counters correct
- [ ] Balance calculations correct
- [ ] Aggregations correct
- [ ] Reports accurate
- [ ] Dashboards accurate
- [ ] Analytics data accurate

### Database Schema

**Schema Changes Applied** (if applicable)
- [ ] New tables exist
- [ ] New columns exist
- [ ] Indexes created
- [ ] Constraints applied
- [ ] Old columns removed (if needed)
- [ ] Migration scripts run

**Data Type Verification**
- [ ] Data types correct
- [ ] Data length correct
- [ ] Encoding correct
- [ ] Precision correct
- [ ] Scale correct (for decimals)
- [ ] Defaults applied

---

## Performance Validation

### Benchmark Comparison

**Baseline Comparison**
- [ ] Response time vs. baseline: ±10%
- [ ] Throughput vs. baseline: ±10%
- [ ] Error rate vs. baseline: same
- [ ] Resource usage vs. baseline: ±10%
- [ ] Database query time vs. baseline: ±10%
- [ ] Cache hit rate vs. baseline: ±5%

**Trend Analysis**
- [ ] Performance trend is stable
- [ ] No gradual degradation
- [ ] Metrics not trending down
- [ ] Metrics not trending up unexpectedly
- [ ] Performance consistent across time
- [ ] No suspicious patterns

### Load Testing Results (if done pre-deployment)
- [ ] Current performance meets expectations
- [ ] Scalability acceptable
- [ ] Bottlenecks identified pre-deployment addressed
- [ ] Load test results reproducible
- [ ] Performance under peak load acceptable
- [ ] No performance regressions

### Feature Performance

**New Feature Performance** (if applicable)
- [ ] New feature response time acceptable
- [ ] New feature resource usage acceptable
- [ ] New feature not impacting other features
- [ ] New feature caching working
- [ ] New feature database queries optimized
- [ ] New feature scalable

---

## Issue Detection

### What to Look For

**Red Flags**
- [ ] Any error rate spike (> 2x baseline)
- [ ] Any response time spike (> 2x baseline)
- [ ] Any resource spike (CPU > 85%, Memory > 90%)
- [ ] Any database connection errors
- [ ] Any cascading failures
- [ ] Any data corruption
- [ ] Any security issues
- [ ] Any data loss

**Yellow Flags**
- [ ] Slowly increasing error rate
- [ ] Slowly increasing response time
- [ ] Slowly increasing resource usage
- [ ] Cache hit rate lower than expected
- [ ] Unusual traffic patterns
- [ ] Unusual database patterns
- [ ] New types of errors
- [ ] User complaints starting

### How to Investigate

**If Performance Degrades**
1. Check error logs
2. Check database query logs
3. Check resource usage
4. Profile application
5. Check for memory leaks
6. Review recent code changes
7. Check external dependencies
8. Consider rollback if critical

**If Errors Appear**
1. Check error type
2. Check error frequency
3. Check error source
4. Search error in logs
5. Check for patterns
6. Review recent code changes
7. Check external service status
8. Consider rollback if critical

**If Data Issues Appear**
1. Check data sample
2. Verify migration (if applicable)
3. Check referential integrity
4. Check constraint violations
5. Review transaction logs
6. Compare with backup
7. Assess data impact
8. Develop recovery plan

### Communication During Issues

- [ ] Issue reported to team immediately
- [ ] Severity assessed
- [ ] On-call person notified
- [ ] Stakeholders notified
- [ ] Issue tracked
- [ ] Root cause investigation started
- [ ] Workaround implemented (if possible)
- [ ] Rollback decision made (if critical)

---

## Sign-Off Process

### Verification Checklist

**Technical Sign-Off**
- [ ] All health checks passing
- [ ] No critical errors
- [ ] Performance acceptable
- [ ] Error rates acceptable
- [ ] Data integrity verified
- [ ] Backups running
- [ ] Monitoring working
- [ ] Alerting working

**Functional Sign-Off**
- [ ] Critical features working
- [ ] Known workflows working
- [ ] No obvious UI issues
- [ ] User can complete main tasks
- [ ] No regression identified
- [ ] New features working (if deployed)
- [ ] Feature flags configured correctly

**Operational Sign-Off**
- [ ] Runbooks updated
- [ ] Monitoring dashboards created/updated
- [ ] Alerting configured
- [ ] Team trained
- [ ] Documentation updated
- [ ] On-call rotation notified
- [ ] Post-mortem scheduled (if issues)

### Sign-Off Authority

- [ ] Engineering lead approval: _______________
- [ ] Operations lead approval: _______________
- [ ] Product lead approval: _______________
- [ ] Final approval given: _______________
- [ ] Time of approval: _______________

### Success Declaration

- [ ] Deployment declared successful
- [ ] Monitoring continued for 24 hours
- [ ] Post-deployment review scheduled
- [ ] Stakeholders notified of success
- [ ] Status page updated
- [ ] Incident closed (if any)

---

## Documentation

### Deployment Record

**What to Document**
- [ ] Deployment date and time
- [ ] Code version deployed
- [ ] Team members involved
- [ ] Deployment strategy used
- [ ] Duration of deployment
- [ ] Any issues encountered
- [ ] Any rollbacks performed
- [ ] Performance comparison (before/after)
- [ ] Data verification results
- [ ] Sign-off signatures

### Post-Deployment Report

**Report Contents**
- [ ] Deployment summary
- [ ] Issues encountered
- [ ] Issues resolved
- [ ] Workarounds applied
- [ ] Performance impact
- [ ] Lessons learned
- [ ] Improvements for next time
- [ ] Follow-up actions

### Monitoring Setup

**What to Verify**
- [ ] All dashboards created
- [ ] All alerts configured
- [ ] All metrics being collected
- [ ] All logs being aggregated
- [ ] All traces being captured
- [ ] Historical baselines set
- [ ] Alerting tests completed
- [ ] On-call runbooks updated

---

## 24-Hour Monitoring

After 24 hours, confirm:

- [ ] No unusual patterns
- [ ] No memory leaks (memory usage stable)
- [ ] No gradual performance degradation
- [ ] No database issues
- [ ] No backup issues
- [ ] All systems stable
- [ ] User feedback positive
- [ ] No late-appearing issues

---

## Sign-Off Template

```
DEPLOYMENT SIGN-OFF

Deployment ID: [ID]
Date: [Date]
Time: [Time]
Version: [Version]

Technical Verification: ✓ Pass
- Health checks: PASS
- Error rates: PASS
- Performance: PASS
- Data integrity: PASS

Functional Verification: ✓ Pass
- Critical features: PASS
- Workflows: PASS
- No regressions: PASS

Operational Readiness: ✓ Pass
- Monitoring: PASS
- Alerting: PASS
- Documentation: PASS

DEPLOYMENT SUCCESSFUL

Approved by: [Name]
Time: [Time]
Date: [Date]
```