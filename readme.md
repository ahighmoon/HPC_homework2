# Problem4 (b)

compute.cpp

| function  | timing & latency in -O3                                             | timing & latency in -O0                                              |
| --------- | ------------------------------------------------------------------- | -------------------------------------------------------------------- |
| multi-add | 1.269017 seconds<br />4.188539 cycles/eval<br />1.575412 Gflop/s    | 8.043716 seconds<br />26.617035 cycles/eval<br />0.247673 Gflop/s    |
| division  | 4.179022 seconds<br />13.791518 cycles/eval<br />0.478521 Gflop/s   | 12.820453 seconds<br />42.307923 cycles/eval<br />0.155996 Gflop/s   |
| sqrt      | 9.364293 seconds<br />30.909289 cycles/eval<br />0.213524 Gflos     | 26.953673 seconds<br />88.948128 cycles/eval<br />0.074199 Gflop/s   |
| sin       | 37.791434 seconds<br />124.712700 cycles/eval<br />0.052921 Gflop/s | 93.534323 seconds<br />308.665848 cycles/eval<br />0.021382 Gflop/s  |
| cos       | 45.238150 seconds<br />149.286980 cycles/eval<br />0.044210 Gflop/s | 139.052990 seconds<br />458.876761 cycles/eval<br />0.014383 Gflop/s |


---

compute-vec.cpp

| col1 | col2 | col3 |
| ---- | ---- | ---- |
|      |      |      |
|      |      |      |


---

compute-vec-pipe.cpp
