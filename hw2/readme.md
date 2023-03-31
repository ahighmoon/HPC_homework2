# Problem 2

Timing for the blocked version code for differernt matrix sizes:

Dimension   		Time 	Gflop/s   		  GB/s    		Error

```
        16   0.940969   2.125472  34.007556 0.000000e+00
        64   0.880328   2.272060  36.352955 3.776222e-09
       112   0.867486   2.306224  36.899583 7.457857e-10
       160   0.870898   2.304564  36.873016 1.091394e-10
       208   0.870912   2.314536  37.032572 6.639311e-11
       256   0.882998   2.280034  36.480544 1.682565e-11
       304   0.901927   2.242755  35.884081 1.045919e-11
       352   0.886877   2.262156  36.194493 5.229595e-12
       400   0.919569   2.227130  35.634088 3.410605e-12
       448   0.965189   2.235799  35.772785 2.046363e-12
       496   1.065612   2.061192  32.979073 1.364242e-12
       544   1.057167   2.131970  34.111523 1.364242e-12
       592   0.932122   2.225832  35.613309 7.958079e-13
       640   0.952024   2.202835  35.245359 5.684342e-13
       688   1.391884   1.871770  29.948315 4.547474e-13
       736   1.132509   2.112240  33.795836 4.547474e-13
       784   1.343163   2.152637  34.442198 4.547474e-13
       832   1.122377   2.052538  32.840611 2.842171e-13
       880   1.262039   2.159908  34.558520 2.842171e-13
       928   1.476659   2.164830  34.637274 3.410605e-13
       976   1.795821   2.070839  33.133428 3.410605e-13
      1024   1.012141   2.121725  33.947594 1.705303e-13
      1072   1.154860   2.133462  34.135396 1.705303e-13
      1120   1.317228   2.133159  34.130547 1.705303e-13
      1168   1.478995   2.154725  34.475594 2.273737e-13
      1216   1.730838   2.077660  33.242553 2.273737e-13
      1264   1.893284   2.133318  34.133081 2.842171e-13
      1312   2.169996   2.081481  33.303699 2.273737e-13
      1360   2.434194   2.066767  33.068276 2.842171e-13
      1408   2.628640   2.123767  33.980274 2.842171e-13
      1456   2.902786   2.126665  34.026645 2.273737e-13
      1504   3.473727   1.958745  31.339915 2.842171e-13
      1552   3.608272   2.072077  33.153231 2.842171e-13
      1600   3.906348   2.097099  33.553591 2.842171e-13
      1648   4.394179   2.037154  32.594467 2.842171e-13
      1696   4.781807   2.040401  32.646415 2.842171e-13
      1744   5.213708   2.034805  32.556875 2.842171e-13
      1792   5.937216   1.938479  31.015667 2.842171e-13
      1840   6.276373   1.985065  31.761037 2.842171e-13
      1888   7.130219   1.887700  30.203207 2.842171e-13
      1936   7.515289   1.931080  30.897288 3.410605e-13
      1984   7.854626   1.988518  31.816286 3.410605e-13
```

---

# Problem 4 (b)

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

Then the VEC_LEN is 4, the normal execution yields:

time = 1.322662
flop-rate = 2.354612 Gflop/s

The vecorized code yields:

time = 1.280265

flop-rate = 2.893360 Gflop/s

There's no much difference in my execution so I don't know what/how to explain. My compile command is g++ -std=c++11 -O3 -march=native compute-vec.cpp -ftree-vectorize -fopt-info-vec-optimized. I am compiling the code using gcc 12.2.0 on a Windows machine with Inter i5-10210U chip.

---

compute-vec-pipe.cpp


M = 1:


time = 1.238109
flop-rate = 2.992088 Gflop/s

time = 1.229141
flop-rate = 3.013968 Gflop/s

time = 1.211443
flop-rate = 3.058208 Gflop/s


M = 2: 


time = 1.292003
flop-rate = 2.410646 Gflop/s

time = 1.320351
flop-rate = 2.359010 Gflop/s

time = 1.324384
flop-rate = 2.351743 Gflop/s


M = 3:


time = 1.429195
flop-rate = 1.766589 Gflop/s

time = 1.632165
flop-rate = 1.546986 Gflop/s

time = 1.410861
flop-rate = 1.789586 Gflop/s


M = 4:


time = 1.291951
flop-rate = 1.497712 Gflop/s

time = 1.340657
flop-rate = 1.443241 Gflop/s

time = 1.301906
flop-rate = 1.486120 Gflop/s


M = 5:


time = 1.352020
flop-rate = 0.994889 Gflop/s

time = 1.332747
flop-rate = 1.009200 Gflop/s

time = 1.490212
flop-rate = 0.902640 Gflop/s

M = 6:


time = 1.429470
flop-rate = 0.528297 Gflop/s

time = 1.382441
flop-rate = 0.546300 Gflop/s

time = 1.399024
flop-rate = 0.539829 Gflop/s


Summary: The running time wasn't obviously impacted, but the flop-rate is getting lower when M is increased.
