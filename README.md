# Dynex MEXC Balance Monitor

![Dynex MEXC Balance Monitor dashboard with balance, in and out charts and transaction feed](assets/dynex-mexc-balance-monitor-live-dashboard-in-out-charts.png)

Exchange balances move the Dynex market, and the movements are easy to miss in a chain explorer. Dynex MEXC Balance Monitor is a WordPress dashboard on [logicencoder.com](https://logicencoder.com/dynex-mexc-balance-monitor/) that shows the DNX balance held by the monitored MEXC wallet, every deposit and withdrawal as a live feed, and charts of net flow, volume and balance over time. It serves holders and analysts who follow exchange flows of Dynex.

## Tech stack

| Layer | Technologies |
|---|---|
| Plugin | PHP and WordPress with a shortcode, a REST API and an admin settings page |
| Front end | JavaScript, CSS, WebSocket and AJAX updates, interactive charts |
| Data worker | A Python worker that scans the Dynex chain and posts summaries to the site |
| Storage | WordPress database tables trimmed by scheduled jobs |

## Balance and totals

The top of the dashboard shows the current balance, total incoming and outgoing DNX, transaction counts and the progress of the chain scan. A message board beside it carries announcements from the site owner. The numbers refresh while the page is open, so a visitor sees a new deposit or withdrawal within seconds of the scan finding it.

## Live IN/OUT feed

The feed lists transactions as they arrive, with direction, amount, address and time. A direction filter, a search box and a minimum amount keep it readable, and the list can be exported as CSV. The minimum amount affects only the feed; totals always count every transaction.

## Charts and analytics

Four interactive charts show net flow, incoming against outgoing volume, transaction count and balance over time, each with its own period of hourly, daily or weekly steps and a timespan from 24 hours to 30 days. A histogram groups transactions by size, a table lists the biggest transactions above a configurable whale threshold, and a ranking shows the addresses with the highest volume.

## Administration

The settings page holds the API key used by the data worker, the poll mode, thresholds, storage caps, diagnostics and row purging. Access to the dashboard can be limited to logged-in users or to allowed IP ranges, with allow and ban lists that accept network ranges.

## Scope and limits

The dashboard covers the monitored MEXC Dynex wallet and the data the worker has scanned so far; the scan progress indicator shows how far the history reaches.

---

Private code: [dynex-mexc-balance-monitor-plugin](https://github.com/logicencoder/dynex-mexc-balance-monitor-plugin)

See [REPOS.md](REPOS.md) for related repositories.

**[Logic Encoder](https://logicencoder.com)** · [GitHub](https://github.com/logicencoder) · [Contact](https://logicencoder.com/contact/)
