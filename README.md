# Production Ready Checklist

A comprehensive guide to ensure your application is production-ready before deployment. This checklist covers security, performance, monitoring, testing, deployment, and operational excellence.

## Table of Contents

1. [Security Checklist](#security-checklist)
2. [Performance Checklist](#performance-checklist)
3. [Testing Checklist](#testing-checklist)
4. [Monitoring & Logging](#monitoring--logging)
5. [Database Checklist](#database-checklist)
6. [Deployment Checklist](#deployment-checklist)
7. [Post-Deployment](#post-deployment)
8. [Templates](#templates)

---

## Security Checklist

### Environment & Secrets
- [ ] All environment variables documented in `.env.example`
- [ ] No credentials in code or git history
- [ ] Secrets manager configured (HashiCorp Vault, AWS Secrets Manager, etc.)
- [ ] API keys rotated and versioned
- [ ] Database credentials stored securely
- [ ] Private keys for JWT/encryption stored safely
- [ ] Environment variables validated on startup

### Authentication & Authorization
- [ ] Authentication mechanism implemented and tested
- [ ] Password hashing uses strong algorithm (bcrypt, Argon2)
- [ ] Session management configured securely
- [ ] JWT tokens have appropriate expiration
- [ ] Token refresh mechanism implemented
- [ ] CORS properly configured
- [ ] CSRF protection enabled
- [ ] Rate limiting on login endpoints
- [ ] Authorization checks on all protected routes
- [ ] Role-based access control (RBAC) implemented

### Data Protection
- [ ] HTTPS/TLS enabled for all endpoints
- [ ] HTTP Strict Transport Security (HSTS) header set
- [ ] Sensitive data encrypted at rest (if applicable)
- [ ] Database encryption enabled
- [ ] Backups encrypted
- [ ] Data transmission encrypted
- [ ] Sensitive logs masked/redacted
- [ ] PII handling compliant with regulations (GDPR, CCPA, etc.)

### API Security
- [ ] Input validation on all endpoints
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (output encoding)
- [ ] Dependency vulnerabilities scanned
- [ ] API rate limiting configured
- [ ] API keys cannot be exposed in client-side code
- [ ] GraphQL/REST query complexity limits set
- [ ] File upload validation (size, type, content)
- [ ] Arbitrary file access prevented
- [ ] Third-party service integration securely handled

### Headers & Security Settings
- [ ] Content-Security-Policy header set
- [ ] X-Frame-Options header set (prevent clickjacking)
- [ ] X-Content-Type-Options set to nosniff
- [ ] Referrer-Policy configured
- [ ] Security headers validated
- [ ] Server version not exposed in headers
- [ ] Debug mode disabled in production

---

## Performance Checklist

### Database
- [ ] Database queries profiled and optimized
- [ ] N+1 queries eliminated
- [ ] Query execution plans reviewed
- [ ] Appropriate indexes created
- [ ] Slow query log analyzed
- [ ] Connection pooling configured
- [ ] Query timeout set
- [ ] Database statistics up-to-date
- [ ] Inefficient views/stored procedures identified
- [ ] Query caching configured (if applicable)

### Caching
- [ ] Application-level caching configured (Redis/Memcached)
- [ ] Cache invalidation strategy implemented
- [ ] Cache TTLs optimized
- [ ] Cache hit rates monitored
- [ ] CDN configured for static assets
- [ ] HTTP caching headers set appropriately
- [ ] Cache stampede prevention implemented
- [ ] Cache size limits enforced

### Code Optimization
- [ ] Expensive operations profiled
- [ ] CPU-intensive operations identified
- [ ] Memory usage profiled
- [ ] Unnecessary object allocations eliminated
- [ ] String concatenations optimized (StringBuilder, etc.)
- [ ] Loop efficiency reviewed
- [ ] Recursive functions have base cases
- [ ] Third-party library versions up-to-date

### Assets & Frontend
- [ ] Static assets minified (JS, CSS)
- [ ] Images compressed and optimized
- [ ] Asset versioning/cache busting implemented
- [ ] JavaScript bundles not oversize
- [ ] CSS not duplicated
- [ ] Unused code removed
- [ ] Asset loading optimized (lazy loading)
- [ ] Async/defer attributes used for JS

### Response Times
- [ ] API response time benchmarked
- [ ] Response time SLAs defined
- [ ] P95/P99 response times measured
- [ ] Slow endpoints identified and optimized
- [ ] Load testing completed
- [ ] Concurrent user limits identified

---

## Testing Checklist

### Unit Tests
- [ ] Unit tests written for business logic
- [ ] Test coverage > 80% for critical paths
- [ ] Edge cases tested
- [ ] Error conditions tested
- [ ] Tests passing locally
- [ ] Tests independent and isolated

### Integration Tests
- [ ] Database interactions tested
- [ ] External service integrations tested (with mocks)
- [ ] API endpoint tests written
- [ ] Request/response validation tested
- [ ] Error handling tested

### End-to-End Tests
- [ ] Critical user journeys tested
- [ ] Happy path tested
- [ ] Error scenarios tested
- [ ] E2E tests passing

### Security Testing
- [ ] SQL injection tested
- [ ] XSS vulnerability scanned
- [ ] CSRF protection tested
- [ ] Authentication bypass tested
- [ ] Authorization checks tested
- [ ] Dependency vulnerabilities scanned (npm audit, composer audit)
- [ ] OWASP Top 10 review completed

### Performance Testing
- [ ] Load testing completed
- [ ] Stress testing completed
- [ ] Spike testing completed
- [ ] Database queries optimized based on load test
- [ ] API response times acceptable under load

### Manual Testing
- [ ] Critical workflows manually tested
- [ ] UI/UX verified on different browsers
- [ ] Mobile responsiveness verified
- [ ] Accessibility compliance checked
- [ ] Cross-browser compatibility verified

---

## Monitoring & Logging

### Application Monitoring
- [ ] Error tracking configured (Sentry, etc.)
- [ ] Performance monitoring enabled (New Relic, Datadog)
- [ ] Uptime monitoring configured
- [ ] Alerting configured for critical errors
- [ ] Application health check endpoint available
- [ ] Metrics collection enabled

### Logging
- [ ] Centralized logging configured (ELK, Splunk)
- [ ] Log levels appropriate (DEBUG disabled in production)
- [ ] Sensitive data not logged
- [ ] Log rotation configured
- [ ] Log retention policy defined
- [ ] Log queries performant
- [ ] Structured logging implemented

### Database Monitoring
- [ ] Database performance monitoring enabled
- [ ] Slow query log enabled and monitored
- [ ] Connection pool monitoring enabled
- [ ] Disk space alerts configured
- [ ] Backup success monitored

### Infrastructure Monitoring
- [ ] CPU usage monitored
- [ ] Memory usage monitored
- [ ] Disk space monitored
- [ ] Network bandwidth monitored
- [ ] Server alerts configured
- [ ] Load balancer health checks configured

### Alerting
- [ ] High error rate alert configured
- [ ] Performance degradation alert configured
- [ ] Service down alert configured
- [ ] Database down alert configured
- [ ] Disk space alert configured
- [ ] Memory alert configured
- [ ] On-call rotation configured
- [ ] Alert escalation path defined

---

## Database Checklist

### Schema & Integrity
- [ ] Schema migrations tested
- [ ] Database constraints defined (FK, UNIQUE, NOT NULL)
- [ ] Schema documentation updated
- [ ] Index strategy finalized
- [ ] Database naming conventions followed
- [ ] Reserved keywords not used in names

### Data Integrity
- [ ] Data validation implemented (at application level)
- [ ] Referential integrity enforced
- [ ] Cascading deletes tested
- [ ] Data consistency verified
- [ ] Transactions used where appropriate
- [ ] Deadlock prevention reviewed

### Backup & Recovery
- [ ] Backup strategy defined (frequency, retention)
- [ ] Backups automated and scheduled
- [ ] Backup restoration tested
- [ ] Restore time (RTO) measured
- [ ] Restore point objective (RPO) defined
- [ ] Backup storage location secured
- [ ] Backup encryption enabled
- [ ] Disaster recovery plan documented

### Replication & Failover
- [ ] Database replication configured (if applicable)
- [ ] Replication lag monitored
- [ ] Failover process tested
- [ ] Read replicas configured (if applicable)
- [ ] Replica consistency verified

---

## Deployment Checklist

### Pre-Deployment
- [ ] All tests passing
- [ ] Code reviewed and approved
- [ ] Database migrations written and tested
- [ ] Environment-specific configurations prepared
- [ ] Rollback plan documented
- [ ] Deployment window scheduled
- [ ] Stakeholders notified
- [ ] Team briefed on deployment

### Deployment Process
- [ ] Deployment checklist reviewed
- [ ] Feature flags configured for gradual rollout
- [ ] Blue-green deployment or canary deployment ready
- [ ] Database migrations executed in proper order
- [ ] Configuration files deployed correctly
- [ ] Environment variables verified
- [ ] Secrets deployed securely
- [ ] Service dependencies verified

### Deployment Verification
- [ ] Application starts without errors
- [ ] Health checks pass
- [ ] Database connectivity verified
- [ ] External service connectivity verified
- [ ] API endpoints responding
- [ ] Critical workflows tested
- [ ] Error rates normal
- [ ] Performance metrics acceptable

---

## Post-Deployment

### Monitoring
- [ ] Error rates monitored closely (first 30 minutes)
- [ ] Performance metrics monitored
- [ ] User-facing issues reported and tracked
- [ ] Database performance verified
- [ ] Cache hit rates verified
- [ ] External service integrations working

### Validation
- [ ] Critical functionality verified working
- [ ] No data corruption observed
- [ ] Log messages appropriate and informative
- [ ] Alerts functioning correctly
- [ ] Backup process started successfully
- [ ] Monitoring dashboards updated

### Documentation
- [ ] Changes documented
- [ ] Deployment notes recorded
- [ ] Known issues documented
- [ ] Migration notes documented
- [ ] Rollback information saved

### Follow-up
- [ ] Deployment retrospective scheduled (if issues occurred)
- [ ] Continuous monitoring for 24 hours
- [ ] Performance baseline updated
- [ ] Team debriefing scheduled
- [ ] Lessons learned captured

---

## Templates

### Deployment Plan Template

```
# Deployment Plan - [Date]

## Deployment Information
- **Deployment Window:** [Start Time] - [End Time]
- **Expected Duration:** [X minutes]
- **Risk Level:** [Low/Medium/High]

## What's Being Deployed
- [Feature/Fix 1]
- [Feature/Fix 2]

## Pre-Deployment Checklist
- [ ] All tests passing
- [ ] Code reviewed
- [ ] Database migrations tested
- [ ] Rollback plan ready

## Deployment Steps
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Rollback Plan
- Trigger: [What would cause rollback]
- Steps:
  1. [Rollback step 1]
  2. [Rollback step 2]

## Verification Steps
1. [Verification 1]
2. [Verification 2]

## Communication
- **Stakeholders Notified:** [List]
- **Status Updates:** [How often]
- **Escalation Contact:** [Name]

## Post-Deployment
- Monitor period: 24 hours
- Monitoring focus: [Items to monitor]
```

### Rollback Procedure Template

```
# Rollback Procedure

## When to Rollback
- [Condition 1]
- [Condition 2]

## Pre-Rollback
- [ ] Alert team
- [ ] Notify stakeholders
- [ ] Assess impact
- [ ] Get approval

## Rollback Steps
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Post-Rollback Verification
- [ ] Application running
- [ ] Data integrity verified
- [ ] Backups consistent

## Post-Rollback Communication
- [ ] Update status
- [ ] Notify stakeholders
- [ ] Schedule investigation

## Investigation
- [ ] Root cause analysis
- [ ] Timeline of events
- [ ] Lessons learned
```

### Post-Deployment Verification Template

```
# Post-Deployment Verification

## Date: [Date]
## Deployed By: [Name]
## Version: [Version]

## Infrastructure Checks
- [ ] All servers running
- [ ] Load balancer health check passing
- [ ] Database connectivity verified
- [ ] Cache service responding

## Application Checks
- [ ] Home page loads
- [ ] Login/authentication working
- [ ] Critical workflows functional
- [ ] APIs responding with correct data
- [ ] Error logs no unusual errors

## Performance Checks
- [ ] Response times normal
- [ ] Error rate normal
- [ ] Database queries performant
- [ ] Cache hit rates good

## Data Checks
- [ ] Database migrations applied
- [ ] Data integrity verified
- [ ] Backups running
- [ ] Replication healthy

## Issues Found
- [ ] Issue 1: [Description]
  - Severity: [Critical/High/Medium/Low]
  - Action: [Action]

## Approval
- [ ] Verified by: [Name]
- [ ] Timestamp: [Time]
```

---

## How to Use This Checklist

1. **Before Each Deployment:** Review applicable sections
2. **During Development:** Reference for best practices
3. **Team Onboarding:** Share with new team members
4. **Process Improvement:** Update based on lessons learned
5. **Automation:** Automate checks where possible (linting, testing, security scanning)

## Contributing

Found something missing? Have improvements?
1. Create an issue with your suggestion
2. Submit a pull request with improvements
3. Share your deployment experiences

## License

MIT License - Feel free to use and modify for your team

---

Maintained by Preksha Shah, Head of Engineering. More engineering work and writing at [preksha-shah.vercel.app](https://preksha-shah.vercel.app) and on [LinkedIn](https://www.linkedin.com/in/preksha-shah-065552183/).