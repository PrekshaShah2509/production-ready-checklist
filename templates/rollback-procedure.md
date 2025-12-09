# Rollback Procedure Template

Use this template to execute a production rollback safely and systematically.

---

## Incident Information

**Rollback ID:** `ROLLBACK-2024-01-15-001`
**Original Deployment ID:** `DEPLOY-2024-01-15-001`
**Time Detected:** [Time]
**Time Decision Made:** [Time]
**Rollback Initiated:** [Time]

---

## Rollback Team

**Rollback Lead:** [Name] - [Phone]
**Database Admin:** [Name] - [Phone]
**Operations:** [Name] - [Phone]
**On-Call Person:** [Name] - [Phone]

**Escalation Contact:** [Name] - [Phone]
**Executive Contact:** [Name] - [Phone]

---

## Incident Summary

**What Went Wrong:**
[Description of the issue]

**Impact:**
- **Users Affected:** [Number/Percentage]
- **Services Affected:** [List of services]
- **Duration:** [Time duration]
- **Business Impact:** [Financial/operational impact]
- **Severity:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low

**Symptoms:**
- [ ] High error rate (>5%)
- [ ] Response time spike (>2x baseline)
- [ ] Service unavailability
- [ ] Data corruption
- [ ] Database connectivity issues
- [ ] Memory leak detected
- [ ] Security issue detected
- [ ] Other: _______________

---

## Rollback Decision

**Decision:** ☐ ROLLBACK  ☐ CONTINUE & FIX

**Decision Made By:** _________________ Time: _______

**Reason for Rollback:**
___________________________________________________________________

**Estimated Impact of Rollback:**
- Data loss: [Description or "None"]
- Service downtime: [Duration estimate]
- User impact: [Description]

**Approval:**
- [ ] Engineering Lead approved
- [ ] Operations Lead approved
- [ ] Product Lead approved
- [ ] Executive approved (if critical)

---

## Pre-Rollback Preparation

### Notification
- [ ] Notify rollback team
- [ ] Alert on-call person
- [ ] Notify stakeholders: "Investigating issue, potential rollback"
- [ ] Prepare customer communication
- [ ] Assemble incident response team
- [ ] Join war room/video conference

### Assessment
- [ ] Document current application state
- [ ] Take snapshot of current logs
- [ ] Document error patterns
- [ ] Assess data integrity
- [ ] Verify rollback data available
- [ ] Confirm backup integrity

### Preparation
- [ ] Review rollback procedure
- [ ] Prepare rollback scripts
- [ ] Verify rollback scripts tested
- [ ] Identify previous stable version
- [ ] Confirm database backup available
- [ ] Prepare communication templates

---

## Rollback Execution

### Phase 1: Preparation (T-5 minutes)

- [ ] Final confirmation of rollback decision
- [ ] All team members ready
- [ ] Communication channels open
- [ ] Monitoring dashboards open
- [ ] Logs being captured
- [ ] Backup status verified
- [ ] Rollback scripts verified

**Ready Status:** ☐ READY  ☐ NOT READY

### Phase 2: Code Rollback

**Step 1: Stop Current Services**
- [ ] Signal graceful shutdown
- [ ] Wait for requests to complete (max 60 seconds)
- [ ] Force stop if necessary
- [ ] Verify services stopped
- [ ] Check no processes running
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 2: Revert Code**
- [ ] Identify previous stable version: _______________
- [ ] Pull previous version from repository
- [ ] Verify code reverted
- [ ] Verify build successful
- [ ] Verify no errors in build logs
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 3: Start Previous Version**
- [ ] Start services with previous version
- [ ] Verify services started
- [ ] Check health checks
- [ ] Wait for warm-up
- [ ] Verify no startup errors
- [ ] Check application responding
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

### Phase 3: Database Rollback (if applicable)

**Database Rollback Required:** ☐ Yes  ☐ No

If yes:

**Step 1: Stop Application**
- [ ] Stop application services
- [ ] Confirm all connections closed
- [ ] Wait for final transactions to complete
- **Time:** _______ minutes

**Step 2: Prepare for Restore**
- [ ] Document current database state
- [ ] Verify backup integrity
- [ ] Confirm backup date: _______________
- [ ] Confirm backup size: _______________
- [ ] Verify backup access
- **Time:** _______ minutes

**Step 3: Restore Database**
- [ ] Initiate database restore
- [ ] Monitor restore progress
- [ ] Verify restore completion
- [ ] Check restore logs for errors
- [ ] Verify data integrity
- [ ] Run data validation queries
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

**Step 4: Verify Database Health**
- [ ] Database connections working
- [ ] Query performance acceptable
- [ ] Replication healthy (if applicable)
- [ ] No corruption detected
- [ ] Data consistency verified
- **Status:** ☐ Verified  ☐ Issues Found

### Phase 4: Configuration Rollback

- [ ] Revert environment variables
- [ ] Revert feature flags
- [ ] Revert load balancer config
- [ ] Revert CDN config (if applicable)
- [ ] Verify configuration loaded
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

### Phase 5: Verification

- [ ] Application responding
- [ ] Health checks passing
- [ ] Database connectivity verified
- [ ] Cache connectivity verified
- [ ] Basic functionality tested
- [ ] No errors in logs
- [ ] Error rate returned to normal
- [ ] Response time returned to normal
- **Time:** _______ minutes
- **Status:** ☐ Success  ☐ Failed

---

## Post-Rollback Verification

### Immediate (0-5 minutes)
- [ ] Application responding normally
- [ ] Error rate normal
- [ ] Response time normal
- [ ] Health checks passing
- [ ] No critical errors

**Status:** ☐ Verified  ☐ Issues Found

### Short-Term (5-30 minutes)
- [ ] Error rate remains normal
- [ ] Response time remains normal
- [ ] Resource usage normal
- [ ] Database stable
- [ ] Cache stable
- [ ] External services responding
- [ ] No cascading failures

**Status:** ☐ Verified  ☐ Issues Found

### Extended (30 min - 24 hours)
- [ ] All metrics normal
- [ ] No data corruption
- [ ] Backups running
- [ ] Replication healthy
- [ ] All features working
- [ ] Users able to complete workflows
- [ ] No new issues appearing

**Status:** ☐ Verified  ☐ Issues Found

---

## Data Assessment

### Data Loss
**Expected Data Loss:** [Description]
**Actual Data Loss:** [Description]
**Acceptable:** ☐ Yes  ☐ No, escalate

### Data Integrity
- [ ] Referential integrity maintained
- [ ] Constraints intact
- [ ] No orphaned records
- [ ] Balances correct
- [ ] Counts accurate

**Integrity Status:** ☐ Good  ☐ Issues Found

---

## Communication

### Immediate Notification
- [ ] Rollback team notified
- [ ] Stakeholders notified: Time: _______
- [ ] Customers notified: Time: _______
- [ ] Status page updated: Time: _______

### Communication Template
```
INCIDENT UPDATE: Rollback Completed

We experienced a critical issue with the deployment at [time].
We have rolled back to the previous stable version at [time].

CURRENT STATUS:
- Service: OPERATIONAL
- Error Rate: Normal
- Performance: Normal

IMPACT:
- Downtime: [Duration]
- Affected Users: [Number]
- Data Loss: [None / Description]

NEXT STEPS:
- Investigation underway
- Post-mortem scheduled for [Date] at [Time]
- Updates will be posted every [interval]

Thank you for your patience.
```

---

## Post-Rollback Actions

### Immediate (Next 1 hour)
- [ ] Monitor system stability
- [ ] Respond to customer issues
- [ ] Gather data for incident analysis
- [ ] Document what happened
- [ ] Assign investigation lead

### Short-Term (Next 24 hours)
- [ ] Complete root cause analysis
- [ ] Identify contributing factors
- [ ] Document findings
- [ ] Develop prevention measures
- [ ] Schedule post-mortem meeting

### Follow-Up (Next week)
- [ ] Conduct post-mortem
- [ ] Document lessons learned
- [ ] Implement prevention measures
- [ ] Update deployment procedures
- [ ] Team training/debrief

---

## Sign-Off

**Rollback Completed:** ☐ Yes  ☐ No
**Time Completed:** _______________________
**Application Stable:** ☐ Yes  ☐ No
**Data Integrity Verified:** ☐ Yes  ☐ No

**Rollback Lead Sign-Off:** _________________ Date: _______
**Operations Lead Sign-Off:** _________________ Date: _______
**Data Integrity Verified By:** _________________ Date: _______

**Rollback Status:** ☐ SUCCESSFUL  ☐ PARTIAL SUCCESS  ☐ FAILED

---

## Incident Report Link
[Link to incident report in incident tracking system]

---

## Follow-Up Meeting
**Post-Mortem Scheduled:** [Date] at [Time]
**Meeting Link:** [Link]
**Attendees:** [List of people]

---

## Lessons Learned

**What Went Wrong:**
- [Root cause 1]
- [Root cause 2]
- [Root cause 3]

**How to Prevent:**
- [Prevention 1]
- [Prevention 2]
- [Prevention 3]

**Process Improvements:**
- [Improvement 1]
- [Improvement 2]

**Owner:** _________________ Deadline: __________