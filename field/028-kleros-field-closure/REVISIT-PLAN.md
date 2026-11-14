# Kleros — Revisit Plan

**Scheduled:** 2027-02 (3 months), 2027-05 (6 months)
**Trigger conditions:** see below
**Responsible:** whoever holds the Lead role at that time

## What to check

### On-chain

Query the same DisputeResolver on Arbitrum One:
- address: 0xb5526d022962a1fff6ed32c93e8b714c901f4323
- topic0: 0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995

Collect:
- total disputes (current baseline: 342)
- unique senders (current: 11)
- court distribution
- top senders

### Public sources

- Kleros changelog (docs.kleros.io/changelog)
- Kleros blog (blog.kleros.io)
- Lemon blog (lemon.me/blog)
- Kleros LinkedIn / X

Look for:
- new Kleros Enterprise partners
- new court launches
- Lemon announcements about dispute volume
- regulatory changes in Argentina

### Templates

- Fetch top policyURIs
- Check whether new templates appear
- Check whether Lemon/generic split changes

## Trigger conditions (check earlier than 2027-02)

Fire a check if any of these happen before schedule:

1. Total disputes > 500 (48% growth).
2. New operator with > 50 disputes.
3. Public announcement of new Kleros Enterprise
   partner.
4. Regulatory change in Argentina (new Resolución
   or modification of 893/2025).
5. Kleros / Lemon / Mendoza public statement about
   scaling.

## Response at revisit

After data collection:

- If growth is significant (>30% delta) and not
  single-operator: reopen Kleros as active field.
- If growth is flat or single-operator: extend
  revisit to 2027-08.
- If field is dead (no disputes in 60 days): archive
  permanently.

## How to execute

A new session picks up handoff-current and this
file. The revisit is itself a Run (field/029 or
later). Output: same format as original runs
(RUN.md, SYNTHESIS.md, raw data).

## Baseline numbers (2026-11-14)

- Disputes: 342
- Unique senders: 11
- Dominant operator: 0xe66f7f8a (143)
- Second operator: 0xd0d5fad9 (131)
- Lemon template: 95
- Generic template: 74
- Unique templates: 173
- Monthly average: ~14
- Peak month: 2026-09 (96)
- Last month (partial): 2026-11 (13 in 9 days)
