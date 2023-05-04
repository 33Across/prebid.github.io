---
layout: analytics
title: 33Across
description: 33Across Analytics Adapter
modulecode: 33across
gdpr_supported: true
usp_supported: true
gvl_id: 58
enable_download: true
---

#### About

This analytics adapter collects data about the performance of your ad slots
for each auction run on your site. The data is sent at the earliest opportunity
for each auction to provide a more complete picture of your ad performance.

The analytics adapter is free to use!
However, the publisher must work with our account management team to obtain
a Publisher/Partner ID (PID). If you are already using the 33Across PID,
you may use your existing PID with the analytics adapter.

The 33Across privacy policy is at <https://www.33across.com/privacy-policy/>.

#### Analytics Options

{: .table .table-bordered .table-striped }
| Name      | Scope    | Example | Type  | Description |
|-----------|----------|---------|-------|-------------|
| `pid`     | required | 12345   | `int` | 33Across PID (Publisher ID) |
| `timeout` | optional | 10000   | `int` | Milliseconds to wait after last seen auction transaction before sending report. |

#### Configuration

The data is sent at the earliest opportunity for each auction to provide
a more complete picture of your ad performance, even if the auction is interrupted
by a page navigation. At the latest, the adapter will always send the report
when the page is unloaded, at the end of the auction, or after the timeout,
whichever comes first.

In order to guarantee consistent reports of your ad slot behavior, we recommend
including the GPT Pre-Auction Module (`gptPreAuction` if compiling from source).
This module is included by default when Prebid is downloaded.

Enable the 33Across Analytics Adapter in Prebid.js using the analytics provider `33across`
and options as seen in the example below.

#### Example Configuration

```js
pbjs.enableAnalytics({
    provider: '33across',
    options: {
        /**
         * The 33Across PID (PID).
         */
        pid: 12345,
        /** 
         * Timeout in milliseconds after which an auction report 
         * will be sent regardless of auction state.
         * [optional]
         */
        timeout: 10000
    }
});
```
