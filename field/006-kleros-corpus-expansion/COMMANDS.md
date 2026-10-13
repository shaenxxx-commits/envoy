# Run 006 — Commands

Exact command executed on nova (2026-10-13).

## Environment

- Python venv: /tmp/envoy-keccak (pycryptodome, keccak)
- RPC: https://arb1.arbitrum.io/rpc
- Head block at run: 514 507 160

## Paginated eth_getLogs

Command:

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
    print("head:", head)

    found = {}
    for i in range(10):
        to_block   = head - i*10_000_000
        from_block = to_block - 10_000_000 + 1
        r = rpc("eth_getLogs",[{
            "fromBlock": hex(from_block),
            "toBlock":   hex(to_block),
            "address":   CONTRACT,
            "topics":    [TOPIC0]
        }])
        if "error" in r:
            print(f"chunk {i:>2}: ERROR {r['error']['message'][:70]}")
            time.sleep(2)
            continue
        logs = r["result"]
        print(f"chunk {i:>2}: blocks {from_block}..{to_block} -> {len(logs)} events")
        for log in logs:
            did = int(log["topics"][1],16)
            if did not in found:
                found[did] = {
                    "block": int(log["blockNumber"],16),
                    "arbitrable": "0x"+log["topics"][2][-40:],
                }
        time.sleep(1)

    print()
    print("=== unique disputes:", len(found), "===")
    for did in sorted(found):
        f = found[did]
        print(f"id={did:>4}  block={f['block']}  arbitrable={f['arbitrable']}")
    PYEOF

## Chunk breakdown (raw)

    head: 514507160
    chunk  0: blocks 504507161..514507160 -> 54 events
    chunk  1: blocks 494507161..504507160 -> 93 events
    chunk  2: blocks 484507161..494507160 -> 4 events
    chunk  3: blocks 474507161..484507160 -> 3 events
    chunk  4: blocks 464507161..474507160 -> 2 events
    chunk  5: blocks 454507161..464507160 -> 9 events
    chunk  6: blocks 444507161..454507160 -> 9 events
    chunk  7: blocks 434507161..444507160 -> 3 events
    chunk  8: blocks 424507161..434507160 -> 1 events
    chunk  9: blocks 414507161..424507160 -> 0 events

    === unique disputes: 178 ===

Full ID list preserved in DISPUTES.md.
