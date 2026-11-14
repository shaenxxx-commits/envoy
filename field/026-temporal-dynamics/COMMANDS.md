# Run 026 — Commands

Executed on nova, 2026-11-14.

## Timestamp sampling

    python3 << 'PYEOF'
    import json, subprocess, time
    from collections import Counter, defaultdict
    from datetime import datetime, timezone

    RPC = "https://arb1.arbitrum.io/rpc"

    def rpc(method, params):
        payload = json.dumps({"jsonrpc":"2.0","method":method,"params":params,"id":1})
        out = subprocess.run(
            ["curl","-s","-X","POST",RPC,"-H","Content-Type: application/json",
             "-d",payload,"--max-time","30"],
            capture_output=True, text=True
        ).stdout
        return json.loads(out)

    with open('/tmp/envoy_run025.json') as f:
        recs = {int(k): v for k, v in json.load(f).items()}

    items = sorted(recs.items(), key=lambda x: x[1]["block"])

    N = 40
    step = max(1, len(items)//N)
    samples = items[::step]
    if items[-1] not in samples:
        samples.append(items[-1])

    block_ts = []
    for did, r in samples:
        b = r["block"]
        res = rpc("eth_getBlockByNumber", [hex(b), False])
        if "result" in res and res["result"]:
            ts = int(res["result"]["timestamp"], 16)
            block_ts.append((b, ts))
        time.sleep(0.05)

    def ts_for_block(b):
        if b <= block_ts[0][0]: return block_ts[0][1]
        if b >= block_ts[-1][0]: return block_ts[-1][1]
        for i in range(len(block_ts)-1):
            b0, t0 = block_ts[i]
            b1, t1 = block_ts[i+1]
            if b0 <= b <= b1:
                frac = (b-b0)/(b1-b0) if b1 > b0 else 0
                return int(t0 + frac*(t1-t0))
        return block_ts[-1][1]

    by_month = Counter()
    by_month_operator = defaultdict(Counter)
    for did, r in items:
        ts = ts_for_block(r["block"])
        dt = datetime.fromtimestamp(ts, tz=timezone.utc)
        key = f"{dt.year}-{dt.month:02d}"
        by_month[key] += 1
        by_month_operator[key][r.get("from","")[:10]] += 1

    for m in sorted(by_month):
        print(f"  {m}: {by_month[m]:>4}")
    PYEOF

## Range

    block range: 274289504 .. 522734131
    time range: 2024-11-14 .. 2026-11-09
    timestamps sampled: 44
