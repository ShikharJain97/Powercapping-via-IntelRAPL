# Powercapping-via-IntelRAPL
This repo contains necessary documents and scripts to generate data corresponding to application of powercapping and its effects on kernel execution.
Currently these scripts supports intel microarchtectures , where atleast package power domain must be there.
This tool instruments the c-source code which has marking related to opening and closing of SCOPS, with memory fencing, MSR read calls, Precise-C timers, Enables PAPI based measurement [if supported by the Benchmark for ex. polybench]
The generated CSV will have Energy expenditure, Execution Time, Dynamic events such as [L1,L2,LL cache-misses], Core/Uncore frequency etc. w.r.t applied powercaps
Only Short Powercaps are changed , as we observed no "interesting" changes with respect to other "knobs" like Long powercaps, Short or Long cap window.
I have generated data regarding Multiple benchmarks : Polybench, Polybench-NN, all stencils in polybench-ACC {for ROSE accelarator}, open-earth Benchmarks, Large DL-Models like resnets, mobilenet, vggnet, googlenet, alexnet etc. Micro-architectures are Broadwell, Rocketlake etc.
It is discovered many cases where enforcing energy-savings via powercapping brings more fruitful results than core-frequnecy modulation [DVFS]. Like for some stencils jacobi-2d both energy consumption and execution time savings happen on application of short powercaps.   

