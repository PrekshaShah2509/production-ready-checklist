# Security Checklist

Comprehensive security checklist for production applications. Covers OWASP Top 10, authentication, data protection, API security, and infrastructure security.

## Table of Contents

1. [Environment & Secrets](#environment--secrets)
2. [Authentication & Authorization](#authentication--authorization)
3. [Data Protection](#data-protection)
4. [API Security](#api-security)
5. [Input Validation & Output Encoding](#input-validation--output-encoding)
6. [Session Management](#session-management)
7. [Infrastructure Security](#infrastructure-security)
8. [Dependency Security](#dependency-security)
9. [OWASP Top 10 Mapping](#owasp-top-10-mapping)

---

## Environment & Secrets

### Secret Management
- [ ] Secrets manager configured (Vault, AWS Secrets Manager, HashiCorp)
- [ ] No hardcoded secrets in code
- [ ] Environment variables not logged
- [ ] `.env` files not committed to git
- [ ] `.env.example` created without secrets
- [ ] Secret rotation policy defined
- [ ] Old secrets revoked
- [ ] Audit trail for secret access enabled

### API Keys & Credentials
- [ ] API keys have expiration dates
- [ ] API keys scoped to minimum required permissions
- [ ] API key rotation automated where possible
- [ ] Separate keys for different environments
- [ ] Public and private keys stored separately
- [ ] Database credentials not in application code
- [ ] Third-party API credentials secured

### Configuration Management
- [ ] Configuration validated on startup
- [ ] Invalid configuration fails fast
- [ ] Feature flags secured
- [ ] Debug mode disabled in production
- [ ] Stack traces not exposed to users
- [ ] Error messages don't leak sensitive info

---

## Authentication & Authorization

### Password Security
- [ ] Passwords hashed with strong algorithm (bcrypt, Argon2)
- [ ] Password salt included
- [ ] Minimum password length enforced (12+ characters)
- [ ] Password complexity requirements considered
- [ ] Password history prevents reuse
- [ ] Password expiration policy (if required)
- [ ] Forgotten password flow secure
- [ ] Password reset tokens expire quickly
- [ ] Passwords never logged or displayed

### Authentication Implementation
- [ ] Authentication mechanism documented
- [ ] Multi-factor authentication (MFA) available
- [ ] MFA enforced for admin accounts
- [ ] Session tokens secure and random
- [ ] Session timeout configured
- [ ] Concurrent session limits enforced
- [ ] Account lockout after failed attempts
- [ ] Account lockout duration reasonable
- [ ] Login attempts logged and monitored
- [ ] Rate limiting on authentication endpoints

### JWT & Token Security
- [ ] JWT tokens signed with strong algorithm (RS256, not HS256 for public validation)
- [ ] Token expiration set appropriately
- [ ] Token refresh mechanism implemented
- [ ] Token claims validated
- [ ] Token revocation possible (blacklist or short expiry)
- [ ] Sensitive data not in JWT payload
- [ ] Token storage secure (httpOnly cookies preferred)

### OAuth2 & SSO
- [ ] OAuth2 provider properly configured
- [ ] State parameter used in OAuth flow
- [ ] PKCE implemented for mobile/SPA apps
- [ ] Redirect URIs whitelisted
- [ ] Scope permissions minimal
- [ ] Refresh token rotation implemented
- [ ] SSO session timeout configured

### Authorization
- [ ] Role-based access control (RBAC) implemented
- [ ] Least privilege principle applied
- [ ] Authorization checks on every protected resource
- [ ] Authorization checks server-side (not relying on client)
- [ ] Admin routes require explicit admin role
- [ ] User can only access own data
- [ ] Cross-user data access prevented
- [ ] Permission changes take effect immediately
- [ ] Audit log for permission changes

---

## Data Protection

### Encryption at Rest
- [ ] Sensitive data encrypted at rest
- [ ] Database encryption enabled
- [ ] Encryption keys stored separately from data
- [ ] Encryption algorithm modern (AES-256)
- [ ] Backups encrypted
- [ ] File storage encrypted
- [ ] Old data securely deleted

### Encryption in Transit
- [ ] HTTPS/TLS enabled for all endpoints
- [ ] TLS version 1.2 or higher
- [ ] Strong cipher suites configured
- [ ] Certificate from trusted CA
- [ ] Certificate not self-signed in production
- [ ] Certificate chain complete
- [ ] Certificate expiration monitored
- [ ] Mixed content (HTTP/HTTPS) prevented
- [ ] HSTS header set (Strict-Transport-Security)
- [ ] HSTS preload considered

### Data Classification & Handling
- [ ] Data classified by sensitivity
- [ ] PII handling documented
- [ ] GDPR/CCPA compliance considered
- [ ] Data retention policy defined
- [ ] Data deletion process documented
- [ ] User data can be exported
- [ ] User can request data deletion
- [ ] Right to be forgotten implemented

### Sensitive Data in Logs
- [ ] Passwords never logged
- [ ] API keys never logged
- [ ] Credit card data never logged
- [ ] PII masked in logs
- [ ] Sensitive query parameters redacted
- [ ] Request/response bodies sanitized
- [ ] Log access restricted
- [ ] Log retention policy defined

---

## API Security

### Input Validation
- [ ] All input validated on server-side
- [ ] Data type validation
- [ ] Data length validation
- [ ] Data format validation (email, phone, etc.)
- [ ] Whitelist validation used (not blacklist)
- [ ] Special characters escaped
- [ ] File uploads validated (type, size, content)
- [ ] File upload storage outside web root
- [ ] Arbitrary file access prevented
- [ ] Path traversal prevented

### SQL Injection Prevention
- [ ] Parameterized queries used
- [ ] ORM used correctly (not concatenating SQL)
- [ ] Raw SQL avoided
- [ ] Dynamic SQL sanitized
- [ ] SQL injection testing done
- [ ] Error messages don't reveal database structure

### XSS Prevention
- [ ] Output encoded based on context
- [ ] HTML encoding for HTML context
- [ ] JavaScript encoding for JS context
- [ ] URL encoding for URL context
- [ ] CSS encoding for CSS context
- [ ] Content Security Policy (CSP) header set
- [ ] XSS testing done
- [ ] User input never directly in HTML
- [ ] Template auto-escaping enabled

### CSRF Protection
- [ ] CSRF tokens generated for state-changing requests
- [ ] CSRF tokens validated
- [ ] SameSite cookie attribute set
- [ ] CORS properly configured
- [ ] Preflight requests handled
- [ ] Origin header validated
- [ ] CSRF testing done

### Rate Limiting & DDoS Protection
- [ ] Rate limiting configured
- [ ] Rate limiting by user/IP
- [ ] Rate limit headers returned to clients
- [ ] Exponential backoff for retries
- [ ] DDoS mitigation configured (WAF, CDN)
- [ ] Bot detection enabled
- [ ] Unusual traffic patterns monitored

### API Versioning & Deprecation
- [ ] API versioning strategy clear
- [ ] Old API versions have deprecation timeline
- [ ] Breaking changes communicate in advance
- [ ] Clients notified of deprecation
- [ ] Migration path documented

---

## Session Management

### Session Configuration
- [ ] Session tokens secure and random
- [ ] Session token length sufficient (256+ bits)
- [ ] Session timeout configured (reasonable duration)
- [ ] Idle timeout configured
- [ ] Absolute timeout configured
- [ ] Logout invalidates session
- [ ] Session data encrypted
- [ ] Session storage secure

### Session Security
- [ ] HttpOnly flag set on session cookies
- [ ] Secure flag set on session cookies (HTTPS only)
- [ ] SameSite attribute set
- [ ] Session fixation prevented
- [ ] Session hijacking prevented
- [ ] Cross-session attacks prevented
- [ ] Concurrent session limits enforced
- [ ] Session activity monitored

---

## Infrastructure Security

### Web Server Security
- [ ] Security headers configured:
  - [ ] X-Frame-Options (prevent clickjacking)
  - [ ] X-Content-Type-Options: nosniff
  - [ ] Content-Security-Policy
  - [ ] Referrer-Policy
  - [ ] Permissions-Policy
- [ ] Server software version hidden
- [ ] Unnecessary modules disabled
- [ ] Directory listing disabled
- [ ] Symbolic links restricted

### Network Security
- [ ] Firewall configured
- [ ] Inbound ports minimized
- [ ] Outbound traffic controlled
- [ ] VPN for sensitive access
- [ ] IP whitelisting for admin interfaces
- [ ] DDoS protection enabled
- [ ] WAF (Web Application Firewall) configured
- [ ] Network segmentation implemented

### Server Hardening
- [ ] OS patched and updated
- [ ] Security patches applied promptly
- [ ] Unnecessary services disabled
- [ ] SSH hardened (key-only, port changed)
- [ ] Default credentials changed
- [ ] Account access controlled
- [ ] Sudo access restricted
- [ ] File permissions correctly set

### Database Security
- [ ] Database access restricted
- [ ] Database user has minimal permissions
- [ ] Root/admin account access restricted
- [ ] Database replication encrypted
- [ ] Audit logging enabled
- [ ] Query logging controlled (not logging passwords)
- [ ] Network access restricted to app servers
- [ ] Database backups protected

### Container & Deployment Security
- [ ] Container images scanned for vulnerabilities
- [ ] Base images from trusted sources
- [ ] No secrets in container images
- [ ] Container runs as non-root user
- [ ] Container filesystem read-only where possible
- [ ] Resource limits set
- [ ] Secrets injected at runtime
- [ ] Supply chain security considered

---

## Dependency Security

### Dependency Management
- [ ] Dependency list maintained
- [ ] Direct and transitive dependencies tracked
- [ ] Outdated dependencies identified
- [ ] Security vulnerabilities scanned regularly
- [ ] Vulnerable dependencies updated
- [ ] Dependency update policy documented
- [ ] Security advisories monitored

### Vulnerability Scanning
- [ ] Static Application Security Testing (SAST) done
- [ ] Dynamic Application Security Testing (DAST) done
- [ ] Software Composition Analysis (SCA) done
- [ ] Dependency audit tools configured:
  - [ ] npm audit (JavaScript)
  - [ ] composer audit (PHP)
  - [ ] pip audit (Python)
  - [ ] cargo audit (Rust)
- [ ] CI/CD pipeline includes security scanning
- [ ] Known vulnerabilities list reviewed
- [ ] Zero-day handling plan documented

### Third-Party Risk
- [ ] Third-party service security assessed
- [ ] Third-party SLAs documented
- [ ] Third-party security certifications verified
- [ ] Data sharing with third parties minimized
- [ ] Contracts include security requirements
- [ ] Vendor access audited
- [ ] Vendor access revoked when no longer needed

---

## OWASP Top 10 Mapping

### A1: Injection
- [x] See [Input Validation & Output Encoding](#input-validation--output-encoding)
- [x] See [SQL Injection Prevention](#sql-injection-prevention)
- [ ] NoSQL injection prevented
- [ ] OS command injection prevented
- [ ] LDAP injection prevented

### A2: Broken Authentication
- [x] See [Authentication & Authorization](#authentication--authorization)
- [ ] Brute force attacks mitigated
- [ ] Credential stuffing prevented
- [ ] Default credentials removed

### A3: Sensitive Data Exposure
- [x] See [Data Protection](#data-protection)
- [ ] Data classified
- [ ] Sensitive data encrypted
- [ ] TLS/SSL properly configured

### A4: XML External Entities (XXE)
- [ ] XML parsing disables XXE
- [ ] XML parsing disables DTDs
- [ ] SOAP/XML endpoints secured
- [ ] File uploads don't accept XML from untrusted sources

### A5: Broken Access Control
- [x] See [Authorization](#authorization)
- [ ] Privilege escalation prevented
- [ ] Insecure direct object reference prevented
- [ ] Function level access control implemented

### A6: Security Misconfiguration
- [x] See [Infrastructure Security](#infrastructure-security)
- [ ] Security headers configured
- [ ] Default accounts changed
- [ ] Unnecessary features disabled
- [ ] Security policies enforced

### A7: Cross-Site Scripting (XSS)
- [x] See [XSS Prevention](#xss-prevention)
- [ ] Reflected XSS prevented
- [ ] Stored XSS prevented
- [ ] DOM-based XSS prevented

### A8: Insecure Deserialization
- [ ] Untrusted data not deserialized
- [ ] Deserialization libraries kept updated
- [ ] Object integrity checked
- [ ] Serialization format (JSON preferred over binary)

### A9: Using Components with Known Vulnerabilities
- [x] See [Dependency Security](#dependency-security)
- [ ] Dependencies scanned
- [ ] Vulnerable components removed/updated
- [ ] Update process automated

### A10: Insufficient Logging & Monitoring
- [ ] Security events logged
- [ ] Logs include sufficient context
- [ ] Log access controlled
- [ ] Log retention policy defined
- [ ] Alerting configured for suspicious activity
- [ ] Monitoring dashboard shows security metrics

---

## Security Testing Checklist

- [ ] Security audit completed
- [ ] Penetration testing completed
- [ ] Vulnerability scanning completed
- [ ] Code review for security issues done
- [ ] OWASP Top 10 assessment completed
- [ ] Security regression testing in place
- [ ] Incident response plan documented
- [ ] Security team trained
- [ ] Bug bounty program considered

---

## References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/)
- [CWE Top 25](https://cwe.mitre.org/top25/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)

---

## Updates & Contributions

Last Updated: [Date]
Maintained By: [Team/Person]

Found security issues? See SECURITY.md in root for responsible disclosure.