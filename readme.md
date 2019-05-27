# 性能对比

## Rust

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:8088

Running 30s test @ http://127.0.0.1:8088
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    12.73ms    5.60ms 139.21ms   79.48%
    Req/Sec     2.61k   350.77     4.64k    75.17%
  933703 requests in 30.03s, 114.87MB read
  Socket errors: connect 0, read 220, write 0, timeout 0
Requests/sec:  31094.89
Transfer/sec:      3.83MB
```

## Go

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:8888

Running 30s test @ http://127.0.0.1:8888
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     9.60ms   15.04ms 482.25ms   94.78%
    Req/Sec     4.33k   535.38     7.77k    77.06%
  1549978 requests in 30.01s, 189.21MB read
  Socket errors: connect 0, read 233, write 0, timeout 0
Requests/sec:  51642.66
Transfer/sec:      6.30MB
```

## Python
```
$ wrk -t12 -c400 -d30s http://127.0.0.1:5000

Running 30s test @ http://127.0.0.1:5000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   139.14ms   38.48ms 265.74ms   76.05%
    Req/Sec    70.69     30.04   171.00     66.93%
  15665 requests in 30.10s, 2.48MB read
  Socket errors: connect 0, read 1735, write 26, timeout 0
Requests/sec:    520.48
Transfer/sec:     84.37KB
```