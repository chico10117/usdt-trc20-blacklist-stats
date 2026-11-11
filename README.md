# USDT-TRC20 blacklist activity on TRON

How often Tether freezes, unfreezes and burns USDT on TRON, counted from the events the USDT-TRC20 contract emits. Updated daily from the [USDT blacklist tracker](https://usdt.chikocorp.com/usdt-blacklist-tracker).

- **Live charts and monthly reports:** https://usdt.chikocorp.com/usdt-blacklist-tracker
- **Latest monthly report:** linked from the tracker, at `https://usdt.chikocorp.com/usdt-blacklist-tracker/YYYY-MM`
- **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Free to use, chart and republish with credit.

Aggregates only: the files hold counts per month and per UTC day. They contain no addresses and no transaction hashes. To check one address, use the [free TRON checker](https://usdt.chikocorp.com/check).

## Files

| File | Rows |
|---|---|
| [`data/usdt-trc20-blacklist-monthly.csv`](data/usdt-trc20-blacklist-monthly.csv) | One per calendar month (UTC) since the first blacklist event |
| [`data/usdt-trc20-blacklist-daily.csv`](data/usdt-trc20-blacklist-daily.csv) | One per UTC day, zero-filled |
| `data/*.json` | The same rows, plus license, citation, sync time and field descriptions |

The same files are served live, refreshed hourly, at `https://usdt.chikocorp.com/data/<file name>`. This repository keeps a daily snapshot with history in git.

## Fields

| Field | Meaning |
|---|---|
| `month` / `date` | Calendar month (`YYYY-MM`) or day (`YYYY-MM-DD`), UTC |
| `freezes` | `AddedBlackList` events |
| `frozen_addresses` | Distinct addresses frozen in the month (monthly file only); an address frozen twice counts once |
| `unfreezes` | `RemovedBlackList` events |
| `burn_events` | `DestroyedBlackFunds` events |
| `usdt_destroyed` | USDT burned by `DestroyedBlackFunds`, exact to 6 decimals |
| `complete` | `false` while the period is still in progress or not yet fully synced |

## Source and method

The USDT-TRC20 contract (`TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t`) emits an event every time Tether changes the blacklist. The events are indexed through TronGrid on a schedule. The tracker page explains the method and its limits in detail. TRON only: Tether runs a separate blacklist on every chain.

## How to cite

> TRON Checker, "USDT-TRC20 blacklist activity on TRON", https://usdt.chikocorp.com/usdt-blacklist-tracker. Licensed under CC-BY-4.0.

Please link to the tracker or to the monthly report you used. GitHub's "Cite this repository" button uses [`CITATION.cff`](CITATION.cff).
