# Run 009 — Commands

Executed on nova, 2026-10-13.

## Single-pass extraction

    /tmp/envoy-keccak/bin/python << 'PYEOF'
    import json, subprocess, time

    RPC = "https://arb1.arbitrum.io/rpc"
    CONTRACT = "0x991d2df165670b9cac3B022f4B68D65b664222ea"
    TOPIC0 = "0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995"

    def rpc(method, params):
        payload = json.dumps({"jsonrpc":"2.0","method":method,"params":params,"id":1})
        out = subprocess.run(
            ["curl","-s","-X","POST",RPC,"-H","Content-Type: application/json",
             "-d",payload,"--max-time","90"],
            capture_output=True, text=True
        ).stdout
        return json.loads(out)

    head = int(rpc("eth_blockNumber",[])["result"],16)
    found = {}
    for i in range(30):
        to_block   = head - i*10_000_000
        from_block = to_block - 10_000_000 + 1
        r = rpc("eth_getLogs",[{
            "fromBlock": hex(from_block),
            "toBlock":   hex(to_block),
            "address":   CONTRACT,
            "topics":    [TOPIC0]
        }])
        if "error" in r:
            continue
        for log in r["result"]:
            did = int(log["topics"][1],16)
            if did not in found:
                found[did] = int(log["blockNumber"],16)
        time.sleep(0.5)

    with open('/tmp/envoy_run009.json','w') as f:
        json.dump(found, f)
    PYEOF

## Raw result

    head: 514511288
    total unique IDs: 296
    id range: 0 .. 295
    missing IDs in range: none
    min block: 274289504
    max block: 514090528

## Chunk events (non-empty only)

    chunk  0: 504511289..514511288 -> 54 events
    chunk  1: 494511289..504511288 -> 93 events
    chunk  2: 484511289..494511288 -> 4 events
    chunk  3: 474511289..484511288 -> 3 events
    chunk  4: 464511289..474511288 -> 2 events
    chunk  5: 454511289..464511288 -> 9 events
    chunk  6: 444511289..454511288 -> 9 events
    chunk  7: 434511289..444511288 -> 3 events
    chunk  8: 424511289..434511288 -> 1 events
    chunk  9: 414511289..424511288 -> 0 events (empty)
    chunk 10: 404511289..414511288 -> 1 events
    chunk 11: 394511289..404511288 -> 4 events
    chunk 12: 384511289..394511288 -> 6 events
    chunk 13: 374511289..384511288 -> 7 events
    chunk 14: 364511289..374511288 -> 16 events
    chunk 15: 354511289..364511288 -> 4 events
    chunk 16: 344511289..354511288 -> 16 events
    chunk 17: 334511289..344511288 -> 13 events
    chunk 18: 324511289..334511288 -> 24 events
    chunk 19: 314511289..324511288 -> 3 events
    chunk 20: 304511289..314511288 -> 12 events
    chunk 21: 294511289..304511288 -> 1 events
    chunk 22: 284511289..294511288 -> 6 events
    chunk 23: 274511289..284511288 -> 4 events
    chunk 24: 264511289..274511288 -> 1 events (id 0)
    chunk 25..29: 0 events
