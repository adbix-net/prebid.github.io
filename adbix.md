---
layout: bidder
title: Adbix
description: Adbix Prebid.js Bidder Adapter
biddercode: adbix
pbjs: true
pbs: false
media_types: banner
tcfeu_supported: false
usp_supported: false
coppa_supported: false
schain_supported: false
dchain_supported: false
floors_supported: false
fpd_supported: false
ortb_blocking_supported: false
prebid_member: false
multiformat_supported: will-not-bid
sidebarType: 1
---

### Note

The Adbix bidding adapter requires publisher setup and approval before use. For setup and publisher documentation, contact [support@adbix.net](mailto:support@adbix.net) or visit [Adbix Publisher Documentation](https://adbix.net/documentation.php).

### Bid Params

{: .table .table-bordered .table-striped }

| Name | Scope | Description | Example | Type |
|:-----|:------|:------------|:--------|:-----|
| `publisherId` | required | Adbix publisher account identifier. | `'40'` | `string` |
| `placementId` | required | Adbix approved ad-unit/placement identifier. | `'175'` | `string` |
| `test` | optional | Enables the Adbix test-bid response for integration testing only. Do not use on live inventory. | `true` | `boolean` |

### Test Parameters

```javascript
var adUnits = [{
  code: 'adbix-test-div',
  mediaTypes: {
    banner: {
      sizes: [[300, 250]]
    }
  },
  bids: [{
    bidder: 'adbix',
    params: {
      publisherId: 'test-publisher',
      placementId: 'test-300x250',
      test: true
    }
  }]
}];
```

### Supported Inventory

The Adbix adapter currently supports banner display inventory. Supported banner formats include 300x250, 336x280, 728x90, 320x50, 320x100, and 160x600.
