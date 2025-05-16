# k6.io
k6 is an open source load testing tool developed by Go language 😍. k6 comes with features, which you can learn all about in the documentation. The main features include:

- CLI tool with developer-friendly APIs.
- Scripting in JavaScript ES2015 / ES6 - with support for local and remote modules
- Checks and limits - for goal-oriented load testing

k6 created its own javascript lib to behave like nodejs, so when building scripts it will use the javascript language but with libs provided by k6.io.
Can I use npm and its libs to create my scripts?

Yes you can, import npm modules or libraries, you can [bundle npm modules with webpack](https://k6.io/docs/using-k6/modules/#bundling-node-modules) and import them in your tests.

### Github k6.io
[github k6.io](https://github.com/k6io/k6)

### Instalar k6.io
There are several ways to install it, and because it is done in Go, everything is easier. Just install the binary on your machine. Here is the link with all the installation possibilities:
[Install k6.io](https://k6.io/docs/getting-started/installation/)

### Install with Docker
We will show you the installation using Docker so you won't need to install anything on your machine.

```bash
$ docker pull loadimpact/k6
```

Now let's run our test mass. The detail below is that since it is in a container, the network that will run is another, so I passed parameters to our Script to search for our domain or API hostname and the volume to load our json.

```bash
$ docker run -v $(pwd):/data \
-e DOMAIN=http://192.168.0.70:8080 \
-i loadimpact/k6 run - <script.js
```
We have already left our script ready, calling POST which sends a json and Get which fetches the information and our infamous ping 😍.

#### Executando k6

```bash
$ k6 run myscript.js
```
Or if you are using **Docker:**
```bash
$ docker run -i loadimpact/k6 run - <myscript.js
```
or

```bash
$  k6 run -e DOMAIN=http://localhost:8080 --vus 100 --duration 20s script.js

```

output:
```bash

          /\      |‾‾| /‾‾/   /‾‾/   
     /\  /  \     |  |/  /   /  /    
    /  \/    \    |     (   /   ‾‾\  
   /          \   |  |\  \ |  (‾)  | 
  / __________ \  |__| \__\ \_____/ .io

  execution: local
     script: script.js
     output: -

  scenarios: (100.00%) 1 scenario, 100 max VUs, 50s max duration (incl. graceful stop):
           * default: 100 looping VUs for 20s (gracefulStop: 30s)


running (20.1s), 000/100 VUs, 1000 complete and 0 interrupted iterations
default ✓ [======================================] 100 VUs  20s

     data_received..................: 1.6 MB 81 kB/s
     data_sent......................: 236 kB 12 kB/s
     http_req_blocked...............: avg=915.78µs min=909ns   med=5.2µs    max=28.05ms p(90)=9.32µs   p(95)=188.61µs
     http_req_connecting............: avg=888.55µs min=0s      med=0s       max=27.65ms p(90)=0s       p(95)=2.91µs  
     http_req_duration..............: avg=2.56ms   min=46.94µs med=1.02ms   max=27.01ms p(90)=6.83ms   p(95)=9.41ms  
       { expected_response:true }...: avg=2.56ms   min=46.94µs med=1.02ms   max=27.01ms p(90)=6.83ms   p(95)=9.41ms  
     http_req_failed................: 0.00%  ✓ 0         ✗ 2000 
     http_req_receiving.............: avg=55.03µs  min=6.34µs  med=36.93µs  max=3.45ms  p(90)=92.03µs  p(95)=112.41µs
     http_req_sending...............: avg=118.26µs min=3.6µs   med=26.56µs  max=25.99ms p(90)=180.94µs p(95)=447.84µs
     http_req_tls_handshaking.......: avg=0s       min=0s      med=0s       max=0s      p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=2.38ms   min=31.4µs  med=916.17µs max=21.12ms p(90)=6.53ms   p(95)=9.19ms  
     http_reqs......................: 2000   99.477445/s
     iteration_duration.............: avg=2s       min=2s      med=2s       max=2.03s   p(90)=2.02s    p(95)=2.03s   
     iterations.....................: 1000   49.738723/s
     vus............................: 100    min=100     max=100
     vus_max........................: 100    min=100     max=100

```