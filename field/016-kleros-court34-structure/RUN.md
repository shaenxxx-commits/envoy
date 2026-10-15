# Field Run 016 — Court 34 Structural Parameters

FIELD: KLEROS
STAGE: STRUCTURAL PARAMETERS
STATUS: CLOSED
RESULT: court 34 is top court; all disputes resolved

## Objective

Close the structural gaps raised by External review
(Run 015) for court 34:
- parent court and court hierarchy;
- existence of courts above 34;
- resolved vs ongoing status across the corpus.

## Method

- courts(uint256) on KlerosCore for courts 30-45.
- disputes(uint256) and currentRuling(uint256) for all
  300 disputes in the current corpus.
- eth_getTransactionByHash on a sample dispute tx.

## Result

### Court hierarchy

| court | parent |
|-------|--------|
| 30    | 1      |
| 31    | 10     |
| 32    | 29     |
| 33    | 1      |
| 34    | 33     |

Chain: 34 -> 33 -> 1 (General Court).

Courts 35..45 do not exist (revert on courts(uint256)).
Court 34 is the highest court ID in this deployment.

### Resolved status

All 300 disputes:
- period = 4 (execution)
- ruled = true

No ongoing disputes in the corpus at time of query.

### Ruling distribution

| ruling | count | meaning (Classic kit)  |
|--------|-------|------------------------|
| 0      |  18   | refuse / invalid       |
| 1      | 138   | accept / yes           |
| 2      | 137   | reject / no            |
| 3      |   6   | non-standard           |
| 4      |   1   | non-standard           |

Rulings 3 and 4 are not standard for the Classic
dispute kit. They imply that at least some court-34
disputes use a multi-option dispute kit.

### DisputeResolver invocation

Sample dispute 295:
- tx to: 0xb5526d022962a1fff6ed32c93e8b714c901f4323
- selector: 0xdc653511
- length: 1188 bytes
- args include courtID=34

Resolver calls KlerosCore internally; courtID is
supplied as an argument.

### Corpus growth during session

Run 006: 178 disputes.
Run 009: 296 disputes.
Run 016: 300 disputes.

The corpus grew by 4 disputes during the working
session. The field is actively producing new
disputes.

## Interpretation

- Court 34 is not a leaf in a larger Agentic-specific
  hierarchy. It is the top court in this deployment.
- All 300 disputes are resolved. The corpus is stable,
  not mid-flight.
- Ruling 3 and 4 indicate multi-option dispute kits
  are used by some disputes, not just Classic.
- The field is live: 4 new disputes appeared during
  the session.

## Decision

Court 34 structure resolved.
- parent = 33 -> 1 (General Court)
- no court above 34
- all corpus disputes resolved
- corpus grew by 4 during session

The structural questions raised by Run 015 External
review are answered except:
- PolicyRegistry URI for court 34 (not exposed by
  courts(34); may require separate contract query)
- disputeKitId per dispute (requires round-level
  query; deferred)

## Next Observation

Remaining structural gap: PolicyRegistry for court 34.
Then Phase 4 (filter assessment) and ROLES status.
