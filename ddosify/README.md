#ddosify 
This tool stress tests our API. You can [go here](https://github.com/ddosify/ddosify) for all the details including installation.

I created a config file to test our ZeroHero API.
You can run it from the config I created or run it manually.

### Using Config json
```bash
$ ddosify -config ddosify/config.config.json
```

### Run ddosify
```bash
$ ddosify -n 10000 -m GET -l linear -h 'Content-Type: application/json' -d 20 -t http://localhost:8080/api/hulk
```
output:
```bash
  Initializing...
🔥 Engine fired.

🛑 CTRL+C to gracefully stop.
✔️  Successful Run: 350    100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00779s
✔️  Successful Run: 725    100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00838s
✔️  Successful Run: 1100   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00840s
✔️  Successful Run: 1475   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00843s
✔️  Successful Run: 1850   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00855s
✔️  Successful Run: 2225   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00921s
✔️  Successful Run: 2600   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00961s
✔️  Successful Run: 2975   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00950s
✔️  Successful Run: 3350   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00962s
✔️  Successful Run: 3725   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00953s
✔️  Successful Run: 4100   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00946s
✔️  Successful Run: 4475   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00900s
✔️  Successful Run: 4850   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00876s
✔️  Successful Run: 5000   100%       ❌ Failed Run: 0        0%       ⏱️  Avg. Duration: 0.00873s

RESULT
-------------------------------------
Step 1
-------------------------------------
Success Count:    5000  (100%)
Failed Count:     0     (0%)

Durations (Avg):
  DNS                  :0.0003s
  Connection           :0.0003s
  Request Write        :0.0002s
  Server Processing    :0.0039s
  Response Read        :0.0002s
  Total                :0.0048s

Status Code (Message) :Count
  201 (Created)    :5000

Step 2
-------------------------------------
Success Count:    5000  (100%)
Failed Count:     0     (0%)

Durations (Avg):
  DNS                  :0.0001s
  Connection           :0.0003s
  Request Write        :0.0001s
  Server Processing    :0.0033s
  Response Read        :0.0001s
  Total                :0.0039s

Status Code (Message) :Count
  200 (OK)    :5000

```

