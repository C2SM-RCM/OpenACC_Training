# README #

This repository contains hands on material and code examples for the Swiss Climate Summer school 2017

# Compile and run on Piz Daint (exampel with handsOn1)
```
module load daint-gpu
module load craype-accel-nvidia60

cd handsOn
make handsOn1
srun -n 1 --time=00:02:00 --res=RESERVATION --gres=gpu:1 -C gpu ./handsOn1/handsOn1 
```
on Tuesday 5.9.2017 use --res=swissclimate1 
on Thursday 7.9.2019 use --res=swissclimate2

--

The code examples are adapted from

git@github.com:rmfarber/ParallelProgrammingWithOpenACC.git

Chapter13
