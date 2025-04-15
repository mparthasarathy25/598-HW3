# 598APE-HW3

This repository contains code for homework 3 of 598APE.

This assignment is relatively simple in comparison to HW1 and HW2 to ensure you have enough time to work on the course project.

In particular, this repository is an implementation of an n-body simulator.

To compile the program run:
```bash
make -j
```

To clean existing build artifacts run:
```bash
make clean
```

The three inputs to run are:
```bash
perf record -g ./main.exe 1000 5000
perf record -g ./main.exe 5 1000000000
perf record -g ./main.exe 1000 100000
```

Commits to check out if interested:
* Final Commit - https://github.com/mparthasarathy25/598-HW3
* Parallelism Commit - https://github.com/mparthasarathy25/598-HW3/tree/d10b1e2c82b686a8b06ff4b65c229eeeba39dd0e
* Local Variables - https://github.com/mparthasarathy25/598-HW3/tree/4d175c60b2b937f2218d1d402c901826279d1063
* Aligned Alloc Attempt Commit - https://github.com/mparthasarathy25/598-HW3/tree/a1f4bd79452eb2c0f80b59124c15be6e8a3009af
* MakeFile Flags Attempt Commit - https://github.com/mparthasarathy25/598-HW3/tree/b92f41ab9705f52b95e7f5ac8538c1450afe98ae
* Sqrt Attempt Commit - https://github.com/mparthasarathy25/598-HW3/tree/d06a8bd5eddfed4597e68bf0b5895ec309215e24


This program assumes the following are installed on your machine:
* A working C compiler (g++ is assumed in the Makefile)
* make
* perf
* C++17 for aligned_alloc

The nbody program is a classic physics simulation whose exact results are unable to be solved for exactly through integration.

Here we implement a simple time evolution where each iteration advances the simulation one unit of time, according to Newton's law of gravitation.

Once compiled, one can call the nbody program as follows, where nplanets is the number of randomly generated planets for the simulation, and timesteps denotes how long to run the simulation for:
```bash
./main.exe <nplanets> <timesteps>
```

In particular, consider speeding up simple run like the following (which runs ~6 seconds on my local laptop under the default setup):
```bash
./main.exe 1000 5000
```

Exact bitwise reproducibility is not required, but approximate correctness (within a reasonable region of the final location).
