# Run 007 — Commands

Command: same as Run 006, but no per-arbitrable filter.

    /tmp/envoy-keccak/bin/python << 'PYEOF'
    import json, subprocess, time
    from collections import Counter

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

    all_events = []
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
            print(f"chunk {i}: ERROR {r['error']['message'][:80]}")
            time.sleep(2)
            continue
        logs = r["result"]
        print(f"chunk {i}: blocks {from_block}..{to_block} -> {len(logs)} events")
        all_events.extend(logs)
        time.sleep(1)

    c = Counter('0x'+log['topics'][2][-40:] for log in all_events)
    print()
    print("=== unique arbitrable contracts:", len(c), "===")
    for addr, n in c.most_common():
        print(f"{n:>4}  {addr}")

    ids = sorted(set(int(log['topics'][1],16) for log in all_events))
    print()
    print("unique dispute IDs:", len(ids))
    print("min:", ids[0], "max:", ids[-1])
    PYEOF

## Raw result

    head: 514509693
    chunk 0: 504509694..514509693 -> 54 events
    chunk 1: 494509694..504509693 -> 93 events
    chunk 2: 484509694..494509693 -> 4 events
    chunk 3: 474509694..484509693 -> 3 events
    chunk 4: 464509694..474509693 -> 2 events
    chunk 5: 454509694..464509693 -> 9 events
    chunk 6: 444509694..454509693 -> 9 events
    chunk 7: 434509694..444509693 -> 3 events
    chunk 8: 424509694..434509693 -> 1 events
    chunk 9: 414509694..424509693 -> 0 events

    === unique arbitrable contracts: 1 ===
     178  0xb5526d022962a1fff6ed32c93e8b714c901f4323

    unique dispute IDs: 178
    min: 118 max: 295
