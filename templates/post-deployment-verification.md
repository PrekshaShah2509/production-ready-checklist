# Post-Deployment Verification Checklist

Use this form to verify application health immediately after deployment.

---

## Deployment Information

**Deployment ID:** `DEPLOY-2024-01-15-001`
**Application:** [Application Name]
**Version:** [Version Number]
**Deployment Time:** [Time]
**Verification Time:** [Time]
**Verified By:** [Name]
**Duration Since Deployment:** [X minutes]

---

## Immediate Checks (0-5 minutes)

### Application Health

**Connectivity**
- [ ] Application URL responds (HTTP 200)
- [ ] Health check endpoint responds
- [ ] All server instances responding
- [ ] Load balancer routing correctly
- [ ] No connection refused errors
- [ ] DNS resolving correctly

**Result:** ☐ PASS  ☐ FAIL

### Service Status

**Process Health**
- [ ] Web server running
- [ ] Application process running
- [ ] Database connections established
- [ ] Cache server responding
- [ ] External services responding
- [ ] Message queue responding

**Result:** ☐ PASS  ☐ FAIL

### Startup Verification

**Application Startup**
- [ ] No startup errors in logs
- [ ] No connection pool errors
- [ ] No initialization failures
- [ ] All services initialized
- [ ] Configuration loaded correctly
- [ ] No missing dependencies

**Result:** ☐ PASS  ☐ FAIL

### Error Monitoring

**Error Rate**
- [ ] Error rate is baseline (±5%)
- [ ] No spike in 5xx errors
- [ ] No spike in 4xx errors
- [ ] No cascade of errors
- [ ] Error log not growing exponentially

**Result:** ☐ PASS  ☐ FAIL

### Critical Errors
- [ ] No database connection errors
- [ ] No null pointer exceptions
- [ ] No out of memory errors
- [ ] No permission denied errors
- [ ] No file not found errors
- [ ] No network timeouts

**Result:** ☐ PASS  ☐ FAIL

### Basic Functionality

**Core Features**
- [ ] Homepage loads
- [ ] Navigation works
- [ ] Links working
- [ ] Images loading
- [ ] CSS/JS loading
- [ ] No obvious UI breaks

**Result:** ☐ PASS  ☐ FAIL

---

## Short-Term Monitoring (5-30 minutes)

### Performance Metrics

**Response Time**
- [ ] Response time p50: _______ ms (baseline: _______ ms)
- [ ] Response time p95: _______ ms (baseline: _______ ms)
- [ ] Response time p99: _______ ms (baseline: _______ ms)
- [ ] Variance from baseline: ☐ <10%  ☐ 10-20%  ☐ >20%

**Status:** ☐ ACCEPTABLE  ☐ CONCERNING

**Throughput**
- [ ] Request rate: _______ req/s
- [ ] Baseline: _______ req/s
- [ ] Stable: ☐ Yes  ☐ No
- [ ] No unusual patterns: ☐ Yes  ☐ No

**Status:** ☐ ACCEPTABLE  ☐ CONCERNING

**Resource Usage**
- [ ] CPU usage: _______ % (limit: 80%)
- [ ] Memory usage: _______ % (limit: 85%)
- [ ] Disk I/O: Normal / Elevated
- [ ] Network bandwidth: Normal / High

**Status:** ☐ ACCEPTABLE  ☐ CONCERNING

### Error Rate Monitoring

**Error Metrics**
- [ ] Error rate: _______ % (baseline: _______ %)
- [ ] 5xx error rate: _______ %
- [ ] 4xx error rate: _______ %
- [ ] No systematic errors: ☐ Yes  ☐ No

**Status:** ☐ ACCEPTABLE  ☐ CONCERNING

### User-Facing Functionality

**Critical Features**
- [ ] Login/authentication working
- [ ] Main workflow working
- [ ] Data operations working
- [ ] Search/filtering working
- [ ] File operations working (if applicable)

**Status:** ☐ PASS  ☐ FAIL

---

## Database Health

**Connectivity**
- [ ] Database connections: _______ / _______ (used/max)
- [ ] Connection pool healthy: ☐ Yes  ☐ No
- [ ] No connection errors: ☐ Yes  ☐ No
- [ ] Replication healthy: ☐ Yes  ☐ N/A

**Status:** ☐ HEALTHY  ☐ CONCERNING

**Performance**
- [ ] Query execution time normal: ☐ Yes  ☐ No
- [ ] Slow queries: _______ (baseline: _______)
- [ ] Index usage correct: ☐ Yes  ☐ No
- [ ] No timeouts: ☐ Yes  ☐ No

**Status:** ☐ HEALTHY  ☐ CONCERNING

**Data Integrity**
- [ ] Data corruption visible: ☐ None  ☐ Minor  ☐ Major
- [ ] Referential integrity: ☐ OK  ☐ Issues
- [ ] Foreign keys intact: ☐ Yes  ☐ No
- [ ] Unique constraints intact: ☐ Yes  ☐ No

**Status:** ☐ VERIFIED  ☐ ISSUES FOUND

---

## Infrastructure Health

**Server Status**
- [ ] All servers healthy
- [ ] CPU usage trending: ☐ Stable  ☐ Up  ☐ Down
- [ ] Memory usage trending: ☐ Stable  ☐ Up  ☐ Down
- [ ] No hardware errors: ☐ Yes  ☐ No

**Status:** ☐ HEALTHY  ☐ CONCERNING

**Load Balancer**
- [ ] All backends available: ☐ Yes  ☐ No
- [ ] Health checks passing: ☐ Yes  ☐ No
- [ ] Traffic distribution even: ☐ Yes  ☐ No

**Status:** ☐ HEALTHY  ☐ CONCERNING

---

## Cache Health

**Cache Status**
- [ ] Cache server responding: ☐ Yes  ☐ No
- [ ] Hit rate: _______ % (baseline: _______ %)
- [ ] Eviction rate: _______ (acceptable: ☐ Yes  ☐ No)
- [ ] No corruption: ☐ Verified  ☐ Issues

**Status:** ☐ HEALTHY  ☐ CONCERNING

---

## Issues Found

**Issue 1**
- **Description:** ___________________________________________________
- **Severity:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low
- **Action Taken:** ___________________________________________________
- **Status:** ☐ Resolved  ☐ Pending  ☐ Escalated

**Issue 2**
- **Description:** ___________________________________________________
- **Severity:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low
- **Action Taken:** ___________________________________________________
- **Status:** ☐ Resolved  ☐ Pending  ☐ Escalated

---

## Sign-Off

### Verification Results Summary

| Component | Status | Notes |
|-----------|--------|-------|
| Application Health | ☐ PASS / ☐ FAIL | _________ |
| Performance | ☐ PASS / ☐ FAIL | _________ |
| Database | ☐ PASS / ☐ FAIL | _________ |
| Infrastructure | ☐ PASS / ☐ FAIL | _________ |
| Errors | ☐ PASS / ☐ FAIL | _________ |

### Overall Status

**Deployment Status:** 
- ☐ SUCCESSFUL
- ☐ SUCCESSFUL WITH MINOR ISSUES
- ☐ REQUIRES ATTENTION
- ☐ ROLLBACK REQUIRED

**Recommendation:**
- ☐ Continue monitoring
- ☐ Monitor closely, report issues
- ☐ Escalate to leadership
- ☐ Begin rollback

---

## Verification Approvals

**Verified By:** _________________ 
**Title:** _________________
**Time:** _________________ 
**Date:** _________________

**Operations Approved:** _________________ Date: _______

**Product Approved:** _________________ Date: _______

**Final Approval:** _________________ Date: _______

---

## Monitoring Schedule

**Next Check:** _________________ (5-10 minutes)
**Extended Check:** _________________ (30 minutes)
**24-Hour Check:** _________________ (24 hours)

---

## Notes & Comments

**What Went Well:**
- ________________________________________________________________
- ________________________________________________________________

**What Could Be Better:**
- ________________________________________________________________
- ________________________________________________________________

**Follow-Up Items:**
1. ________________________________________________________________ (Owner: __________)
2. ________________________________________________________________ (Owner: __________)

---

## Attachments

- [ ] Monitoring dashboard screenshot
- [ ] Log excerpt
- [ ] Performance metrics
- [ ] Error rate graph
- [ ] Incident report (if issues)

---

**Deployment Verification Complete**

Verified By: _________________ Date: _________ Time: _________