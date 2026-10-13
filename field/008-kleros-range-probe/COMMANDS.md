# Run 008 — Commands

Executed on nova, 2026-10-13.
RPC: https://arb1.arbitrum.io/rpc

## Traversal 1: 414M backwards (10 chunks)

    start_block = 414_509_694

    chunk 0: 404509695..414509694 -> 1 events
    chunk 1: 394509695..404509694 -> 4 events
    chunk 2: 384509695..394509694 -> 6 events
    chunk 3: 374509695..384509694 -> 7 events
    chunk 4: 364509695..374509694 -> 16 events
    chunk 5: 354509695..364509694 -> 4 events
    chunk 6: 344509695..354509694 -> 16 events
    chunk 7: 334509695..344509694 -> 13 events
    chunk 8: 324509695..334509694 -> 24 events
    chunk 9: 314509695..324509694 -> 3 events

    total: 94 events
    IDs: 24..117
    arbitrable: 0xb5526d022962a1fff6ed32c93e8b714c901f4323

## Traversal 2: 314M backwards (10 chunks)

    start_block = 314_509_694

    chunk 0: 304509695..314509694 -> 12 events
    chunk 1: 294509695..304509694 -> 1 events
    chunk 2: 284509695..294509694 -> 6 events
    chunk 3: 274509695..284509694 -> 4 events
    chunk 4: 264509695..274509694 -> 1 events
    chunk 5: 254509695..264509694 -> 0 events
    chunk 6: 244509695..254509694 -> 0 events
    chunk 7: 234509695..244509694 -> 0 events
    chunk 8: 224509695..234509694 -> 0 events
    chunk 9: 214509695..224509694 -> 0 events

    total: 24 events
    IDs: 0..23
    arbitrable: 0xb5526d022962a1fff6ed32c93e8b714c901f4323

## Traversal 3: 214M backwards (5 chunks)

    start_block = 214_509_694

    chunk 0: 204509695..214509694 -> 0 events
    chunk 1: 194509695..204509694 -> 0 events
    chunk 2: 184509695..194509694 -> 0 events
    chunk 3: 174509695..184509694 -> 0 events
    chunk 4: 164509695..174509694 -> 0 events

    total below 214M: 0 events
    First non-empty traversal segment ends between
    214M and 254M.

## Command template

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

    start_block = <start>
    all_events = []
    for i in range(10):
        to_block   = start_block - i*10_000_000
        from_block = to_block - 10_000_000 + 1
        r = rpc("eth_getLogs",[{
            "fromBlock": hex(from_block),
            "toBlock":   hex(to_block),
            "address":   CONTRACT,
            "topics":    [TOPIC0]
        }])
        if "error" in r:
            print(f"chunk {i}: ERROR")
            continue
        logs = r["result"]
        print(f"chunk {i}: {from_block}..{to_block} -> {len(logs)} events")
        all_events.extend(logs)
        time.sleep(1)
    PYEOF
