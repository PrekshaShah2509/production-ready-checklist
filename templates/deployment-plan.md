# Deployment Plan Template

Use this template to plan each production deployment systematically.

---

## Deployment Information

**Deployment ID:** `DEPLOY-2024-01-15-001`
**Service/Application:** [Application Name]
**Version:** [Version Number/Git Commit]
**Deployment Date:** [Date]
**Deployment Time:** [Time] - [Time] (Duration: ~XX minutes)
**Time Zone:** [Your Time Zone]
**Environment:** Production

---

## Team & Contacts

**Deployment Lead:** [Name] - [Email] - [Phone]
**Technical Lead:** [Name] - [Email] - [Phone]
**Database Admin:** [Name] - [Email] - [Phone]
**Operations:** [Name] - [Email] - [Phone]
**On-Call Person:** [Name] - [Phone]

**Escalation Contact:** [Name] - [Phone]
**Emergency Contact:** [Name] - [Phone]

---

## What's Being Deployed

### Code Changes
- [ ] Feature 1: [Brief description]
- [ ] Feature 2: [Brief description]
- [ ] Bug Fix 1: [Brief description]
- [ ] Performance improvement: [Brief description]

**Total Changes:** X commits, Y files modified

### Configuration Changes
- [ ] Environment variable changes
- [ ] Feature flag changes
- [ ] Load balancer configuration
- [ ] CDN configuration
- [ ] Database configuration

### Database Changes
- [ ] Schema migration: [Description]
- [ ] Data migration: [Description]
- [ ] Backup before migration: Yes / No

### Dependencies Updated
- [ ] [Dependency Name] v1.0 → v2.0
- [ ] [Dependency Name] v1.5 → v1.6

---

## Risk Assessment

**Risk Level:** ☐ Low  ☐ Medium  ☐ High

**Risk Factors:**
- [ ] Database schema changes
- [ ] Breaking API changes
- [ ] External service dependency changes
- [ ] Infrastructure changes
- [ ] Large code changes
- [ ] New technology introduction
- [ ] Customer-facing changes

**Mitigation Strategies:**
1. [Mitigation strategy 1]
2. [Mitigation strategy 2]
3. [Mitigation strategy 3]

**Contingency Plan:**
- If [issue], then [action]
- If [issue], then [action]

---

## Pre-Deployment Checklist

### Code Quality
- [ ] Code reviewed and approved
- [ ] All tests passing (unit, integration, E2E)
- [ ] Code style checks passing
- [ ] Security scans passing
- [ ] Performance tests acceptable
- [ ] Code coverage acceptable (>80% critical paths)
- [ ] No breaking changes without migration

### Database
- [ ] Migration script written and tested
- [ ] Rollback migration script written and tested
- [ ] Migration tested on staging environment
- [ ] Zero-downtime migration confirmed
- [ ] Backup strategy confirmed
- [ ] Backup taken from production (if applicable)
- [ ] Data integrity verified pre-migration

### Configuration & Secrets
- [ ] Environment variables prepared
- [ ] Secrets prepared (not in code)
- [ ] Configuration values reviewed
- [ ] Feature flags configured
- [ ] A/B test configuration ready (if applicable)
- [ ] Secrets rotated (if needed)
- [ ] No hardcoded credentials

### Infrastructure & Deployment
- [ ] Servers provisioned (if needed)
- [ ] Load balancer rules configured
- [ ] SSL certificates valid
- [ ] CDN configured (if applicable)
- [ ] DNS records ready (if applicable)
- [ ] Rollback procedure tested
- [ ] Blue-green/Canary setup verified (if applicable)

### Monitoring & Alerts
- [ ] Monitoring configured and tested
- [ ] Alerting rules configured and tested
- [ ] Dashboards created/updated
- [ ] Log aggregation configured
- [ ] Baseline metrics recorded
- [ ] Alert recipients confirmed

### Team & Documentation
- [ ] Team trained on new features/changes
- [ ] Runbooks updated
- [ ] Architecture documentation updated
- [ ] Known issues documented
- [ ] Communication plan prepared
- [ ] Rollback procedure documented
- [ ] Post-deployment verification checklist prepared

### Approvals
- [ ] Engineering lead approval: _________________ Date: _______
- [ ] Product lead approval: _________________ Date: _______
- [ ] Operations approval: _________________ Date: _______
- [ ] Security review (if needed): _________________ Date: _______

---

## Deployment Steps

### Pre-Deployment (T-30 minutes to T-0)

**30 Minutes Before**
- [ ] Verify all systems ready
- [ ] Confirm deployment window hasn't changed
- [ ] Notify stakeholders: "Deployment starting soon"
- [ ] Final code/config verification
- [ ] Database backup initiated
- [ ] Confirm backup completion
- [ ] Team members online and ready
- [ ] Communication channels open

**15 Minutes Before**
- [ ] Final status check
- [ ] Team in video conference
- [ ] Monitoring dashboards open
- [ ] Logs being monitored
- [ ] Baseline metrics recorded
- [ ] Review rollback procedure
- [ ] Final go/no-go decision

**Go Decision:** ☐ GO  ☐ NO-GO

If NO-GO, reason: _______________________________________________

### Deployment Execution (T-0 to T+Duration)

**Step 1: Code Deployment**
- [ ] Pull latest code
- [ ] Build application
- [ ] Run tests
- [ ] Create deployment package
- [ ] Copy to servers
- [ ] Verify package integrity
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 2: Database Migration** (if applicable)
- [ ] Take database backup
- [ ] Run migration scripts
- [ ] Verify migration success
- [ ] Check data integrity
- [ ] Verify migration time acceptable
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 3: Configuration Update**
- [ ] Update environment variables
- [ ] Update configuration files
- [ ] Update feature flags
- [ ] Verify configuration loaded
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 4: Stop Old Services** (if applicable)
- [ ] Signal graceful shutdown
- [ ] Wait for requests to complete
- [ ] Stop services
- [ ] Verify services stopped
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 5: Start New Services**
- [ ] Start services
- [ ] Verify services started
- [ ] Check health checks
- [ ] Wait for warm-up
- [ ] Verify no startup errors
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 6: Verification**
- [ ] Health check endpoint responding
- [ ] Application endpoints responding
- [ ] Database connectivity verified
- [ ] Cache connectivity verified
- [ ] Basic functionality tested
- [ ] No critical errors in logs
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 7: Traffic Migration** (if applicable)
- [ ] Monitor error rates
- [ ] Monitor response time
- [ ] Monitor resource usage
- [ ] Gradually shift traffic
- [ ] Monitor final metrics
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Total Deployment Time:** _______ minutes

---

## Post-Deployment Verification

### Immediate (0-5 minutes)
- [ ] Application responding
- [ ] Error rate normal
- [ ] Response time normal
- [ ] Health checks passing
- [ ] No critical errors

**Status:** ☐ Verified  ☐ Issues Found

### Short-Term (5-30 minutes)
- [ ] Error rate remains normal
- [ ] Response time remains normal
- [ ] Resource usage normal
- [ ] Database healthy
- [ ] Cache healthy
- [ ] External services responding

**Status:** ☐ Verified  ☐ Issues Found

### Extended (30 min - 24 hours)
- [ ] All metrics normal
- [ ] No performance degradation
- [ ] No memory leaks
- [ ] Backups running
- [ ] Replication healthy
- [ ] All features working
- [ ] No regression issues

**Status:** ☐ Verified  ☐ Issues Found

---

## Issues & Resolution

### Issue 1
**Description:** ________________________________________________
**Severity:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low
**Resolution:** ________________________________________________
**Time to Resolve:** _________ minutes

### Issue 2
**Description:** ________________________________________________
**Severity:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low
**Resolution:** ________________________________________________
**Time to Resolve:** _________ minutes

### Rollback Decision
**Rollback Required:** ☐ Yes  ☐ No
**Reason (if yes):** _______________________________________________

---

## Sign-Off

**Deployment Completed:** ☐ Yes  ☐ No
**Time Completed:** _______________________
**Deployment Lead Verification:** _________________ Date: _______
**Operations Lead Verification:** _________________ Date: _______
**Product Lead Verification:** _________________ Date: _______

**Status:** ☐ SUCCESSFUL  ☐ SUCCESSFUL WITH ISSUES  ☐ ROLLED BACK

---

## Post-Deployment Notes

**What Went Well:**
- [Note 1]
- [Note 2]

**What Could Be Improved:**
- [Note 1]
- [Note 2]

**Lessons Learned:**
- [Note 1]
- [Note 2]

**Follow-Up Actions:**
1. [Action] - Owner: __________ - Deadline: __________
2. [Action] - Owner: __________ - Deadline: __________

---

## Stakeholder Communication

**Internal Team Notified:** ☐ Yes  Time: __________
**Customers Notified:** ☐ Yes  ☐ No  Time: __________
**Status Page Updated:** ☐ Yes  Time: __________
**Post-Deployment Report Sent:** ☐ Yes  Time: __________

---

## Attachment References

- [ ] Code review link: _______________
- [ ] Test results: _______________
- [ ] Monitoring dashboard: _______________
- [ ] Log file location: _______________
- [ ] Incident report (if applicable): _______________