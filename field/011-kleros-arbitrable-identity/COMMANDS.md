# Run 011 — Commands

Executed on nova, 2026-10-13.

## 1. Arbitrable code

    eth_getCode 0xb5526d...4323 -> 3595 bytes, not a proxy.

## 2. Standard selectors

    name()                 -> revert
    symbol()               -> revert
    decimals()             -> revert
    supportsInterface()    -> revert

Conclusion: not an ERC-20/721.

## 3. Events from arbitrable

    eth_getLogs(address=0xb5526d..., last 5M blocks)

    topic0 counts:
      8  0x394027a5fa6e098a1191094d1719d6929b9abc535fcc0c8f448d6a4e75622276
      7  0x8bd32f430ff060e6bd204709b3790c9807987263d3230c580dc80b5f89e27186

Decoded via keccak256:
    0x394027a5... = Ruling(address,uint256,uint256)
    0x8bd32f43... = DisputeRequest(address,uint256,uint256,uint256,string)

=> ERC-792 Arbitrable interface.

## 4. Transaction receipt decode

    tx 0xa94d5dffa78dd59275af5be4f970267386861e3153afbeabf895139fdf6a6cac

    logs:
      [0] 0xae1eed20... DisputeKitGatedProxy
      [1] 0x991d2df... KlerosCore (DisputeCreation)
      [2] 0x0cfbaca5... DisputeTemplateRegistry (MetaEvidence)
      [3] 0xb5526d... DisputeResolver (DisputeRequest)
      [4] 0xdb9b1e94... (unidentified, large data)

## 5. MetaEvidence decode

    From log[2], DisputeTemplateRegistry:
    Spanish-language consumer dispute template.
    category "Junín", policyURI /ipfs/Qmassb4gk...

## 6. Court distribution

    queried disputes(uint256) for all 296 IDs

    courtID  1: 6
    courtID  3: 8
    courtID 24: 3
    courtID 29: 87
    courtID 31: 21
    courtID 32: 36
    courtID 34: 135
