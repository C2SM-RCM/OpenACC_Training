# README #

This repository contains hands on material (slides) and code examples for openacc training

# Compile and run on Tsa (example with handsOn1)
```
module load PrgEnv-pgi

cd handsOn
make TARGET=gpu handsOn1 # or TARGET=cpu
srun -n 1 --time=00:02:00 -p debug ./handsOn1/handsOn1
```
# Compile and run on Piz Daint (example with handsOn1)

```
module load daint-gpu
module swap PrgEnv-cray/6.0.10 PrgEnv-nvidia 
module load craype-accel-nvidia60

cd handsOn
make TARGET=gpu COMPILER=nvidia handsOn1 # or TARGET=cpu
srun -n 1 -p debug -A d56 -C gpu ./handsOn1/handsOn1 
```
# Compile and run on Mistral
```
module load gcc/7.1.0
module load /sw/rhel6-x64/pgi/pgi-18.10/modulefiles/pgi/18.10
cd handsOn
make COMPILER=pgi TARET=gpu handsOn1
srun -n 1 --partition=gpu --nodes=1 --time=0:05:00 --account=YOURACCOUNT --constraint=k80 ./example_openacc1/example_openacc1
```

The code examples are adapted from

git@github.com:rmfarber/ParallelProgrammingWithOpenACC.git

Chapter13
