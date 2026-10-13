# Run 010 — Commands

Executed on nova, 2026-10-13.

## Sampling and density

    /tmp/envoy-keccak/bin/python << 'PYEOF'
    import json, subprocess, time
    from datetime import datetime, timezone
    from collections import Counter

    RPC = "https://arb1.arbitrum.io/rpc"

    def rpc(method, params):
        payload = json.dumps({"jsonrpc":"2.0","method":method,"params":params,"id":1})
        out = subprocess.run(
            ["curl","-s","-X","POST",RPC,"-H","Content-Type: application/json",
             "-d",payload,"--max-time","30"],
            capture_output=True, text=True
        ).stdout
        return json.loads(out)

    with open('/tmp/envoy_run009.json') as f:
        m = {int(k): v for k, v in json.load(f).items()}

    ids = sorted(m)
    samples = ids[::30]
    if ids[-1] not in samples:
        samples.append(ids[-1])

    for did in samples:
        block = m[did]
        r = rpc("eth_getBlockByNumber",[hex(block), False])
        ts = int(r["result"]["timestamp"], 16)
        print(did, block, datetime.fromtimestamp(ts, tz=timezone.utc))
        time.sleep(0.2)

    # clusters
    c = Counter(m.values())
    multi = {b: n for b, n in c.items() if n > 1}

    # density
    buckets = {}
    for b in m.values():
        bucket = (b // 10_000_000) * 10_000_000
        buckets[bucket] = buckets.get(bucket, 0) + 1
    for b in sorted(buckets):
        print(b, buckets[b])
    PYEOF

## Raw sampled timestamps

    id=  0  block=274289504  2024-11-14 06:14:53 UTC
    id= 30  block=325094694  2025-04-11 01:46:37 UTC
    id= 60  block=341166013  2025-05-27 19:24:50 UTC
    id= 90  block=367330771  2025-08-11 14:52:52 UTC
    id=120  block=440052924  2026-03-09 17:51:22 UTC
    id=150  block=495894648  2026-08-18 17:18:57 UTC
    id=180  block=498315651  2026-08-25 18:07:34 UTC
    id=210  block=503017746  2026-09-08 12:12:04 UTC
    id=240  block=504040281  2026-09-11 11:50:03 UTC
    id=270  block=506420250  2026-09-18 11:22:28 UTC
    id=295  block=514090528  2026-10-12 10:50:59 UTC

## Span and rate

    blocks: 239801024
    seconds: 60237366  (~697.2 days)
    avg sec/block: 0.251
    avg disputes/day: 0.42

## Clusters

    blocks with >1 dispute: 11
    total disputes in clusters: 29
    max in one block: 3
