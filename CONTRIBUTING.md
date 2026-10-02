# Contributing

These repositories are portfolio projects: rebranded, English rewrites of systems built for a
law firm and its clients, running on fictional data so that the architecture can be shown
without the records being shown. They are not products with users, so "contributing" here means
something narrower than usual — and two kinds of issue are genuinely valuable.

## The two most useful things you can report

**A fact about somebody else's API that is wrong.** Several of these repositories document the
behaviour of a third party's API — Meta's WhatsApp Cloud API, a Brazilian federal vehicle
register, Microsoft Graph, OpenSSL's handling of PKCS#12. Every such claim is marked in the docs
as quoted from the vendor, as a dated observation, or as not documented at all, and each carries
the date it was checked. APIs change and dates go stale. If a claim is now wrong, that is the
single most useful issue you can open, and a link to the vendor's own page is all the evidence
needed.

**Anything that looks like real data.** These repositories are supposed to contain no real
person, company, credential or identifier. If something looks like one — a phone number that
could reach somebody, a tax ID whose check digits pass, a court case number that could be a real
case, a token-shaped string — please report it **privately** through the Security tab rather than
in a public issue, and it will be removed the same day. See each repository's `SECURITY.md`.

## Ordinary issues and pull requests

Bug reports, questions about a design decision, and corrections to the prose are all welcome.
Each repository's README argues for its decisions rather than just listing features, so
disagreeing with one of those arguments is a reasonable issue to open.

Feature requests are less likely to go anywhere. These projects are finished at the scope they
were built to, and growing them past that would make them worse at the thing they are for,
which is being readable.

If you open a pull request:

- One logical change per commit, with the message in English, in the imperative, following
  [Conventional Commits](https://www.conventionalcommits.org/) (`feat:`, `fix:`, `docs:`,
  `refactor:`, `test:`, `chore:`). The first line is at most 72 characters with no full stop.
- A body only when the *why* is not obvious from the diff — which, for anything beyond a typo,
  it usually is not. The commit messages in these repositories carry the reasoning, and that is
  deliberate.
- Every repository has CI, and most assert behaviour rather than only running a suite. What CI
  runs varies with what the repository is: the application and library repositories run their
  linter and test suite; `postgres-rls-multitenant-starter` has no linter and instead proves
  its guarantees against a real PostgreSQL and reproduces every way to break them; `portfolio`
  checks the structure of its case studies, its links and its identifiers. Read the workflow
  before assuming a green local run is enough.
- Each repository's `CLAUDE.md` lists its non-negotiable rules — the invariants that must not be
  relaxed. Read it before changing anything it names.

## Running anything

Every repository runs offline, with no credentials and no network call, on fictional data. The
README of each says how in two or three commands, and a demo that needs an API key would be a
bug. If one does not run for you from a fresh clone, that is worth an issue.

## On the use of AI

These projects were built with an AI coding assistant, and each README has a section saying what
it generated, what I rewrote, what I rejected and how the output was validated. Attribution
trailers are deliberately omitted from commit messages — the author is me, the assistant is a
tool, and the transparency lives in the README where someone will actually read it rather than
in commit metadata where they will not.
