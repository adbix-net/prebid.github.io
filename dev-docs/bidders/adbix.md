---
layout: bidder
title: Adbix
description: Adbix Prebid.js Bidder Adapter
pbjs: true
pbs: false
biddercode: adbix
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

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Description](#description)
- [Bid params](#bid-params)
- [Test Parameters](#test-parameters)
- [User Sync](#user-sync)

### Description

Adbix is a global ad network connecting premium publishers with high-quality display demand through a server-to-server bidding engine. The Adbix Prebid.js adapter brings Adbix demand into header bidding auctions for banner inventory via OpenRTB.

The Adbix bidding adapter requires publisher setup and approval before use. For setup and publisher documentation, contact support@adbix.net or visit https://adbix.net/documentation.php

### Bid params

{: .table .table-bordered .table-striped }
| Name          | Scope    | Description                                                               | Example     | Type      |
|---------------|----------|---------------------------------------------------------------------------|-------------|-----------|
| `publisherId` | required | Adbix publisher account identifier                                        | `'12345'`   | `string`  |
| `placementId` | required | Adbix approved ad-unit/placement identifier                               | `'67890'`   | `string`  |
| `test`        | optional | Enables test-bid responses for integration testing only. Not for live use | `true`      | `boolean` |

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

### User Sync

The Adbix adapter supports image pixel user syncs, which are gated by the pixelEnabled config option:

```javascript
pbjs.setConfig({
  userSync: {
    pixelEnabled: true,
    filterSettings: {
      image: {
        bidders: 'adbix',
        filter: 'include'
      }
    }
  }
});
```

Note: Combine the above configuration with any other UserSync configuration. Multiple setConfig() calls overwrite each other and only the last call for a given attribute will take effect.
