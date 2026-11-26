# CSV order reconciliation

Compare an order export with a payment export and hand the review team a list of discrepancies with source row numbers. This sample uses fictional data and was built with Codex assistance.

[Open the interactive sample](https://wjqcluke.github.io/csv-order-check-demo/#sample)

| Order ID | Order export | Payment export | Review result |
| --- | ---: | ---: | --- |
| `001001` | 100.10 | 100.1 | Match |
| `001002` | 80.00 | 88.00 | Amount differs |
| `001003` | 30.00 | — | Missing from payment export |
| `001004` | 10.00 and 10.00 | 10.00 | Duplicate order ID |
| `001005` | Missing amount | 20.00 | Invalid amount |

The sample contains five order IDs, four of which need review. The tool preserves leading zeros, compares valid amounts to the cent, and keeps duplicate rows for review. Missing amounts remain flagged instead of being treated as zero.

## Inputs and deliverables

- Two comma-delimited UTF-8 exports with headers, in the same currency and unit. Each export can contain up to 50,000 records and 10 MiB. Choose the order ID and amount columns for each file.
- The full tool runs locally in the browser, with an exception CSV that retains source row numbers. The linked public sample shows fixed data.
- For a scoped cleanup or reconciliation project, share only the column names, approximate row counts, file formats, and the expected handling of duplicates and refunds in the hiring platform's private conversation. Multi-currency or aggregated payments require separate scoping.

[Report a sample issue](https://github.com/wjqcluke/csv-order-check-demo/issues) using fictional data only. GitHub issues are public.
