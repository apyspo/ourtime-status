# ourtime-status

Serves `https://status.ourtime.ai/service-status.json`, which every installed Ourtime app reads at launch (apyspo/ourtime-frontend#1088, #1089). Hosted on GitHub Pages, independent of the app infrastructure.

```json
{ "state": "normal", "closesOn": null }
```

- `state`: `normal` | `closing` | `closed`
- `closesOn`: `YYYY-MM-DD` when `closing` or `closed`, otherwise `null`
- No free text: all wording lives in the app.

To flip: edit the file, open a PR (the `validate` check must pass), merge. Live in about 10 minutes (Pages caches for 600s). The app remembers the last valid state, so never publish `closing` before the `normal` file has been reachable.
