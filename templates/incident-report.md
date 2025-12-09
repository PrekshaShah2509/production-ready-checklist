# Incident Report Template

Use this form to document production incidents systematically.

---

## Incident Report

### Incident Information

**Incident ID:** `INC-2024-01-15-001`
**Service:** [Service Name]
**Date & Time Detected:** [Date] [Time]
**Date & Time Resolved:** [Date] [Time]
**Total Duration:** [X hours Y minutes]
**Report Created By:** [Name]
**Report Date:** [Date]

---

### Impact Assessment

**Severity Level:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low

**Users Affected:**
- Number of users: [Number / Percentage]
- Geographic regions: [List regions]
- Service affected: [Service names]
- Features affected: [Feature list]

**Business Impact:**
- Revenue impact: $_______ / [Description]
- SLA breach: ☐ Yes  ☐ No
- Data loss: ☐ Yes  ☐ No
- Security impact: ☐ Yes  ☐ No
- Reputation impact: [None / Minor / Significant]

**Timeline**
- Issue started: [Time]
- Issue detected: [Time]
- Detection delay: [X minutes]
- First response: [Time]
- Mitigation started: [Time]
- Issue resolved: [Time]
- MTTR (Mean Time To Resolve): [X hours Y minutes]

---

### Incident Summary

**What Happened:**
[Detailed description of the incident]

**How We Know It Happened:**
[How issue was detected - alerts, user reports, monitoring, etc.]

**Initial Response:**
[Who responded first, what actions were taken]

**Affected Systems:**
- [ ] Web application
- [ ] API
- [ ] Database
- [ ] Cache
- [ ] Message queue
- [ ] External service
- [ ] Infrastructure
- [ ] Other: _________________

---

### Incident Details

**Error Messages / Logs:**
```
[Include relevant error messages]
```

**Affected Endpoints/Features:**
- [Endpoint 1]
- [Endpoint 2]
- [Feature 1]

**Root Cause (Preliminary):**
[Initial assessment of root cause]

---

### Response Actions

**Actions Taken During Incident:**
1. [Action 1] - [Time] - [Owner]
2. [Action 2] - [Time] - [Owner]
3. [Action 3] - [Time] - [Owner]
4. [Action 4] - [Time] - [Owner]

**Mitigation Applied:**
[Description of how issue was mitigated]

**Workarounds:**
[Any workarounds provided to customers]

**Communication:**
- [ ] Status page updated: Time: _______
- [ ] Customers notified: Time: _______
- [ ] Team notified: Time: _______
- [ ] Stakeholders updated: Time: _______

---

### Investigation Findings

**Root Cause Analysis:**
[Detailed root cause]

**Contributing Factors:**
- Factor 1: [Description]
- Factor 2: [Description]
- Factor 3: [Description]

**Why It Happened:**
[Explanation of the underlying cause]

**Why We Didn't Catch It:**
[Description of monitoring/testing gaps]

---

### Investigation Team

**Incident Commander:** [Name]
**Database Lead:** [Name]
**Engineering Lead:** [Name]
**Operations Lead:** [Name]
**Product Lead:** [Name]

---

## Post-Mortem Analysis

### Meeting Information

**Post-Mortem Date:** [Date]
**Post-Mortem Time:** [Time]
**Location/Link:** [Location]
**Attendees:**
- [Name] - [Role]
- [Name] - [Role]
- [Name] - [Role]

**Facilitator:** [Name]
**Scribe:** [Name]

---

### Timeline Reconstruction

| Time | Event | Owner | Impact |
|------|-------|-------|--------|
| HH:MM | [Event] | [Person] | [Impact] |
| HH:MM | [Event] | [Person] | [Impact] |
| HH:MM | [Event] | [Person] | [Impact] |
| HH:MM | [Event] | [Person] | [Impact] |
| HH:MM | [Event] | [Person] | [Impact] |

---

### What Went Well

**Positive Aspects:**
1. [What went well 1]
2. [What went well 2]
3. [What went well 3]

**Why It Worked:**
- [Explanation 1]
- [Explanation 2]
- [Explanation 3]

**Lessons to Keep:**
- Keep doing [Action 1]
- Keep doing [Action 2]
- Keep doing [Action 3]

---

### What Could Be Better

**Areas for Improvement:**
1. [Improvement area 1]
2. [Improvement area 2]
3. [Improvement area 3]

**Why It Was a Problem:**
- [Explanation 1]
- [Explanation 2]
- [Explanation 3]

**Impact of Issues:**
- Delayed detection: [X minutes]
- Delayed response: [X minutes]
- Extended duration: [X minutes]

---

### Root Cause

**Primary Cause:**
[Root cause explanation]

**Contributing Causes:**
1. [Cause 1]
2. [Cause 2]
3. [Cause 3]

**Underlying Issues:**
- [Issue 1]
- [Issue 2]
- [Issue 3]

---

### Prevention Measures

### Short-Term Actions (This Week)
1. **Action:** [Description]
   - **Owner:** [Name]
   - **Deadline:** [Date]
   - **Status:** ☐ Not Started  ☐ In Progress  ☐ Complete

2. **Action:** [Description]
   - **Owner:** [Name]
   - **Deadline:** [Date]
   - **Status:** ☐ Not Started  ☐ In Progress  ☐ Complete

### Medium-Term Actions (This Month)
1. **Action:** [Description]
   - **Owner:** [Name]
   - **Deadline:** [Date]
   - **Status:** ☐ Not Started  ☐ In Progress  ☐ Complete

2. **Action:** [Description]
   - **Owner:** [Name]
   - **Deadline:** [Date]
   - **Status:** ☐ Not Started  ☐ In Progress  ☐ Complete

### Long-Term Actions (This Quarter)
1. **Action:** [Description]
   - **Owner:** [Name]
   - **Deadline:** [Date]
   - **Status:** ☐ Not Started  ☐ In Progress  ☐ Complete

2. **Action:** [Description]
   - **Owner:** [Name]
   - **Deadline:** [Date]
   - **Status:** ☐ Not Started  ☐ In Progress  ☐ Complete

---

### Detection & Monitoring Improvements

**What Alert Could Have Detected This Earlier:**
- [Alert 1]
- [Alert 2]
- [Alert 3]

**Monitoring Gaps Identified:**
- [Gap 1]
- [Gap 2]
- [Gap 3]

**New Alerts to Implement:**
1. [Alert] - Owner: __________ - Deadline: __________
2. [Alert] - Owner: __________ - Deadline: __________

**Monitoring Enhancements:**
1. [Enhancement] - Owner: __________ - Deadline: __________
2. [Enhancement] - Owner: __________ - Deadline: __________

---

### Testing & Validation Improvements

**Test Gaps:**
- [Gap 1]
- [Gap 2]
- [Gap 3]

**New Tests to Add:**
1. [Test] - Owner: __________ - Deadline: __________
2. [Test] - Owner: __________ - Deadline: __________

**Validation Improvements:**
1. [Improvement] - Owner: __________ - Deadline: __________

---

### Process Improvements

**Process Issues:**
1. [Issue 1]
2. [Issue 2]
3. [Issue 3]

**Process Changes:**
1. [Change] - Owner: __________ - Effective Date: __________
2. [Change] - Owner: __________ - Effective Date: __________

**Documentation Updates:**
1. [Update] - Owner: __________ - Deadline: __________
2. [Update] - Owner: __________ - Deadline: __________

---

### Training & Communication

**Team Training Needed:**
- [Training topic 1]
- [Training topic 2]
- [Training topic 3]

**Training Plan:**
1. [Training] - Facilitator: __________ - Date: __________
2. [Training] - Facilitator: __________ - Date: __________

**Communication to Broader Team:**
- [ ] Meeting held
- [ ] Recording shared
- [ ] Summary documented
- [ ] Key lessons shared
- [ ] Q&A session held

---

### Key Learnings

**What We Learned:**
1. [Learning 1]
2. [Learning 2]
3. [Learning 3]

**How This Changes Our Approach:**
- [Change 1]
- [Change 2]
- [Change 3]

**Organizational Knowledge:**
[How this incident improves organizational knowledge and processes]

---

### Follow-Up & Accountability

**Action Items Summary:**

| Action | Owner | Deadline | Priority | Status |
|--------|-------|----------|----------|--------|
| [Action 1] | [Name] | [Date] | ☐ High | ☐ Not Started |
| [Action 2] | [Name] | [Date] | ☐ High | ☐ Not Started |
| [Action 3] | [Name] | [Date] | ☐ Medium | ☐ Not Started |

**Follow-Up Meeting:**
- **Date:** [Date]
- **Time:** [Time]
- **Attendees:** [List]
- **Purpose:** Review action item progress

---

### Approval & Sign-Off

**Post-Mortem Facilitator:** _________________ Date: _______
**Engineering Lead:** _________________ Date: _______
**Operations Lead:** _________________ Date: _______
**Product Lead:** _________________ Date: _______

---

### Additional Notes

**Questions Raised:**
- [Question 1]
- [Question 2]
- [Question 3]

**Future Considerations:**
- [Consideration 1]
- [Consideration 2]

**Related Incidents:**
- [Related incident 1]
- [Related incident 2]

---

### Distribution

**Post-Mortem Shared With:**
- [ ] Engineering team
- [ ] Operations team
- [ ] Product team
- [ ] Executive team
- [ ] All-hands meeting
- [ ] Wiki/documentation
- [ ] Customers (summary)