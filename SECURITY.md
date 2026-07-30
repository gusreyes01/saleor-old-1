# Security Policy

## Support status

This is a legacy application fork maintained on a best-effort basis. Its pinned
Python 3.7, Django 2.2, and Node.js 10 runtimes no longer receive upstream
security updates. Passing CI confirms compatibility with the preserved
toolchain; it does not make the runtime suitable for an unreviewed public
deployment.

Operators should isolate the application, terminate TLS at maintained
infrastructure, restrict access to backing services, rotate credentials, and
review current dependency advisories before every deployment.

## Reporting a vulnerability

Do not disclose vulnerabilities or sensitive data in a public issue. Use the
repository's **Security** tab to submit a private vulnerability report,
including affected code, impact, reproduction steps, and a suggested mitigation
when available. Maintainers will coordinate validation and disclosure through
the private advisory.

## Remediation

Compatible security patches are preferred. If remediation requires a newer
runtime or framework, document the migration, database impact, deployment
sequence, and rollback procedure rather than silently breaking the preserved
application contract.
