# Run 005 — Commands and Raw Responses

Exact commands executed on nova (2026-10-13) and their
raw responses. Preserved for reproducibility.

## 1. Environment check

Command:
    which cast curl python3

Result:
    /usr/bin/curl
    /usr/bin/python3
    (cast not installed)

## 2. Keccak tooling

Command:
    python3 -m venv /tmp/envoy-keccak
    /tmp/envoy-keccak/bin/pip install --quiet pycryptodome

Result: venv created, pycryptodome installed.

## 3. Canonical topic0 for DisputeCreation(uint256,address)

Command:
    /tmp/envoy-keccak/bin/python -c "from Crypto.Hash import keccak; \
    k=keccak.new(digest_bits=256); \
    k.update(b'DisputeCreation(uint256,address)'); \
    print('0x'+k.hexdigest())"

Result:
    0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995

## 4. RPC availability

Command:
    curl -s -X POST https://arb1.arbitrum.io/rpc \
      -H "Content-Type: application/json" \
      -d '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":1}' \
      --max-time 15

Result:
    {"jsonrpc":"2.0","id":1,"result":"0x1eaab53f"}

Head block at time of run: 0x1eaab53f (514 010 431 decimal).

## 5. Contract bytecode

Command:
    curl -s -X POST https://arb1.arbitrum.io/rpc \
      -H "Content-Type: application/json" \
      -d '{"jsonrpc":"2.0","method":"eth_getCode",\
           "params":["0x991d2df165670b9cac3B022f4B68D65b664222ea","latest"],"id":1}' \
      --max-time 15

Result (first 60 chars):
    0x608060405236603757603560317f360894a13ba1a3210667c828492db9

Code length: 372 hex chars (186 bytes). Minimal proxy.

## 6. eth_getLogs (topic0 filter)

Command:
    curl -s -X POST https://arb1.arbitrum.io/rpc \
      -H "Content-Type: application/json" \
      -d '{"jsonrpc":"2.0","method":"eth_getLogs","params":[{\
           "fromBlock":"0x1ea00000",\
           "toBlock":"0x1eaab53f",\
           "address":"0x991d2df165670b9cac3B022f4B68D65b664222ea",\
           "topics":["0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995"]\
           }],"id":1}' \
      --max-time 30

Result: 6 events.

Decoded:
    id= 290  arbitrable=0xb5526d022962a1fff6ed32c93e8b714c901f4323  block=514070587  tx=0x7f019ed24c6c6b40...
    id= 291  arbitrable=0xb5526d022962a1fff6ed32c93e8b714c901f4323  block=514089753  tx=0x706d39bb3bbaf167...
    id= 292  arbitrable=0xb5526d022962a1fff6ed32c93e8b714c901f4323  block=514090351  tx=0xffe74b370db98ea7...
    id= 293  arbitrable=0xb5526d022962a1fff6ed32c93e8b714c901f4323  block=514090414  tx=0xc0e80ed8a95d9e5b...
    id= 294  arbitrable=0xb5526d022962a1fff6ed32c93e8b714c901f4323  block=514090471  tx=0xa1a05ec46a065c15...
    id= 295  arbitrable=0xb5526d022962a1fff6ed32c93e8b714c901f4323  block=514090528  tx=0x976ea99ae07ac924...

## 7. Dispute structure verification

Command:
    curl -s -X POST https://arb1.arbitrum.io/rpc \
      -H "Content-Type: application/json" \
      -d '{"jsonrpc":"2.0","method":"eth_call","params":[{\
           "to":"0x991d2df165670b9cac3B022f4B68D65b664222ea",\
           "data":"0x564a565d0000000000000000000000000000000000000000000000000000000000000127"\
           },"latest"],"id":1}' \
      --max-time 15

Result:
    0x0000000000000000000000000000000000000000000000000000000000000022
    000000000000000000000000b5526d022962a1fff6ed32c93e8b714c901f4323
    0000000000000000000000000000000000000000000000000000000000000004
    0000000000000000000000000000000000000000000000000000000000000001
    000000000000000000000000000000000000000000000000000000006acdcd8d

Decoded (disputes(uint256) returns struct):
    courtID           = 34
    arbitrated        = 0xb5526d022962a1fff6ed32c93e8b714c901f4323
    period            = 4
    ruled             = true
    lastPeriodChange  = 0x6acdcd8d

## 8. Selector reference

Computed locally:
    disputes(uint256)        -> 0x564a565d
    getDispute(uint256)      -> 0xe3a96cbd
    currentRuling(uint256)   -> 0x1c3db16d
    courts(uint256)          -> 0x1f5a0dd2
