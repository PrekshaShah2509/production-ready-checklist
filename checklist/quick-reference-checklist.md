# Quick Reference Checklists

## SECURITY CHECKLIST

```
SECURITY PRE-DEPLOYMENT CHECKLIST
==================================

ENVIRONMENT & SECRETS
[ ] No hardcoded secrets in code
[ ] Environment variables documented
[ ] Secrets manager configured
[ ] API keys rotated
[ ] Database credentials secured

AUTHENTICATION & AUTHORIZATION
[ ] Password hashing strong (bcrypt/Argon2)
[ ] Session management configured
[ ] MFA available for admins
[ ] Authorization checks in place
[ ] Role-based access control (RBAC)

DATA PROTECTION
[ ] HTTPS/TLS enabled
[ ] Sensitive data encrypted
[ ] Backups encrypted
[ ] Data transmission encrypted
[ ] PII handling compliant

API SECURITY
[ ] Input validation on all endpoints
[ ] SQL injection prevention
[ ] XSS prevention (CSP headers)
[ ] CSRF protection enabled
[ ] Rate limiting configured
[ ] Dependency vulnerabilities scanned

INFRASTRUCTURE
[ ] Security headers configured
[ ] Firewall rules configured
[ ] SSH hardened
[ ] Default credentials changed
[ ] Database access restricted

SECURITY TESTING
[ ] SAST performed
[ ] DAST performed
[ ] Code review for security done
[ ] Penetration testing completed
[ ] Dependency audit done

Checked By: _________________ Date: _______
```

---

## PERFORMANCE CHECKLIST

```
PERFORMANCE PRE-DEPLOYMENT CHECKLIST
====================================

DATABASE
[ ] Slow query log analyzed
[ ] Indexes created/optimized
[ ] N+1 queries eliminated
[ ] Query execution plans reviewed
[ ] Connection pooling configured

CACHING
[ ] Caching layer configured (Redis/Memcached)
[ ] Cache invalidation strategy defined
[ ] Cache TTLs optimized
[ ] HTTP caching headers set
[ ] CDN configured

CODE OPTIMIZATION
[ ] Hot paths profiled
[ ] Memory usage optimized
[ ] String operations optimized
[ ] Algorithm complexity acceptable
[ ] Dead code removed

ASSETS
[ ] JavaScript minified
[ ] CSS minified
[ ] Images compressed
[ ] Asset versioning implemented
[ ] Lazy loading configured

API PERFORMANCE
[ ] Response size optimized
[ ] Payload compression enabled
[ ] Pagination implemented
[ ] Field filtering available

LOAD TESTING
[ ] Load test completed
[ ] Response times acceptable
[ ] Stress test completed
[ ] Breaking point identified
[ ] Scaling strategy verified

MONITORING
[ ] Response time tracking enabled
[ ] Performance dashboards created
[ ] Performance alerts configured
[ ] Baseline metrics recorded

Checked By: _________________ Date: _______
```

---

## DEPLOYMENT CHECKLIST

```
DEPLOYMENT DAY CHECKLIST
=======================

PRE-DEPLOYMENT (24 HOURS BEFORE)
[ ] All tests passing
[ ] Code reviewed and approved
[ ] Database migrations tested
[ ] Backups verified
[ ] Team availability confirmed

PRE-DEPLOYMENT (1 HOUR BEFORE)
[ ] Final code verification
[ ] Database backup taken
[ ] Rollback procedure reviewed
[ ] Team members online
[ ] Communication channels open
[ ] Monitoring dashboards ready

DEPLOYMENT EXECUTION
[ ] Code deployed
[ ] Database migrations applied
[ ] Configuration updated
[ ] Services started
[ ] Health checks passing

IMMEDIATE VERIFICATION (0-5 MIN)
[ ] Application responding
[ ] Error rate normal
[ ] Response time normal
[ ] No critical errors
[ ] Health checks passing

SHORT-TERM MONITORING (5-30 MIN)
[ ] Error rate remains normal
[ ] Response time acceptable
[ ] Resource usage normal
[ ] Database stable
[ ] No cascading failures

POST-DEPLOYMENT SIGN-OFF
[ ] Engineering lead approval
[ ] Operations approval
[ ] Product approval
[ ] Monitoring configured
[ ] Team briefing completed

Deployed By: _________________ Date: _______
Verified By: _________________ Date: _______
```

---

## MONITORING SETUP CHECKLIST

```
MONITORING & ALERTING CHECKLIST
================================

METRICS COLLECTION
[ ] Application metrics configured
[ ] Infrastructure metrics configured
[ ] Database metrics configured
[ ] Business metrics configured
[ ] Custom metrics defined

LOG AGGREGATION
[ ] Logs centralized
[ ] Log parsing configured
[ ] Sensitive data masked
[ ] Log retention defined
[ ] Log access restricted

ALERTING
[ ] Service down alert configured
[ ] High error rate alert configured
[ ] Performance degradation alert
[ ] High CPU/memory alert
[ ] Database alerts configured
[ ] Alert testing completed

DASHBOARDS
[ ] System health dashboard created
[ ] Performance dashboard created
[ ] Business metrics dashboard
[ ] Troubleshooting dashboard

MONITORING TOOLS
[ ] Monitoring tool deployed
[ ] Agent/collector configured
[ ] Data retention set
[ ] Visualization enabled

INCIDENT RESPONSE
[ ] Runbooks created
[ ] On-call rotation setup
[ ] Escalation paths defined
[ ] Alert notifications tested

Configured By: _________________ Date: _______
Tested By: _________________ Date: _______
```

---

## CHECKLIST USAGE INSTRUCTIONS

1. Print or save this document
2. Use for each deployment/setup
3. Check off items as completed
4. Date and sign when complete
5. Attach to deployment documentation
6. Reference for continuous improvement

---

## NOTES & CUSTOMIZATION

These are templates. Customize based on:
- Your technology stack
- Your organization's requirements
- Your compliance needs
- Lessons learned from incidents
- Team feedback

Review and update quarterly.