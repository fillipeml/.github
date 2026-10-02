# Security policy

This is the default policy for every repository under this account. Several repositories carry
their own `SECURITY.md` with a scope section specific to what that project handles — a
certificate loader and a webhook verifier have very different attack surfaces — and where one
exists, it takes precedence over this file.

## Reporting

Report privately through the **Security** tab of the repository concerned, using GitHub's
"Report a vulnerability" button. Do not open a public issue: an issue about a disclosure
repeats the disclosure.

You will get an acknowledgement within 72 hours, and a fix or a mitigation plan within 14 days
for anything confirmed.

## What is in scope

**Anything that looks like real data.** These repositories are rebranded rewrites of systems
built for a law firm and its clients, and they are supposed to contain nothing real. A phone
number that could reach somebody, a tax ID whose check digits pass, a court case number that
could be a live case, a credential-shaped string — report it, and it is removed the same day.
This is the most likely finding and the one taken most seriously.

**Anything that weakens a stated guarantee.** Several of these projects make a specific promise
and test it: that a dry run cannot send, that reviewer-approved spreadsheet cells cannot be
overwritten, that a tenant cannot see another tenant's rows, that a private key never reaches
disk or a log, that a webhook refuses an unsigned delivery. A path that defeats one of those is
a vulnerability even if nothing real is at risk in the demo, because the guarantee is what the
repository is for.

**Dependencies.** Dependabot runs monthly on each repository. A vulnerability it has not yet
reported is worth an issue.

## What is not in scope

The demo data itself. Fixture certificates, generated keys, example phone numbers and invented
case numbers are published on purpose, and several are deliberately invalid by construction —
case numbers dated 2099 that fail their own checksum, certificates issued to a fictional
organisation under a reserved country code. Reporting those as leaked secrets is not needed.

Claims about third-party APIs. Each is marked as quoted, as a dated observation, or as not
documented, with the date it was checked. A correction there is a very welcome ordinary issue,
not a vulnerability report.

## Supported versions

The `main` branch and the latest tagged release of each repository. Corrections are made in
place.
