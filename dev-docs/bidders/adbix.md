---
layout: bidder
title: Adbix
description: Prebid Adbix Bidder Adapter
pbjs: true
biddercode: adbix
media_types: banner
coppa_supported: false
tcfeu_supported: false
usp_supported: false
schain_supported: true
sidebarType: 1
---

### Registration

To use the Adbix bidder you will need a valid publisher ID and placement ID from Adbix. For further information, please contact <admin@adbix.net>.

### Bid Params

{: .table .table-bordered .table-striped }
| Name          | Scope    | Description                         | Example            | Type      |
|---------------|----------|-------------------------------------|--------------------|-----------|
| `publisherId` | required | Adbix publisher identifier          | `'test-publisher'` | `string`  |
| `placementId` | required | Adbix placement identifier          | `'test-300x250'`   | `string`  |
| `test`        | optional | Enables the Adbix test response     | `true`             | `boolean` |

### Supported Media Types

- Banner

### User Sync

The adapter may register an image user-sync request when image/pixel syncing is enabled by the publisher.

User-sync endpoint:

```text
https://adbix.net/sync/index.php
