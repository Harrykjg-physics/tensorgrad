<div align="center">
<img align="middle" src="_assets/logo.png" width="500" alt="logo"/>
<h2> Differentiable Programming Tensor Networks </h2>
</div>

[![Build Status](https://travis-ci.org/tangwei94/tensorgrad.svg?branch=master)](https://travis-ci.com/tangwei94/tensorgrad)

### Requirements

* [PyTorch 1.0+](https://pytorch.org/)
* A good GPU card if you are inpatient or ambitious 

### Higher order gradient of free energy

Run this to compute the energy and specific heat of the 2D classical Ising model using Automatic Differentiation through the Tensor Renormalization Group contraction. 

```bash
$ cd 1_ising_TRG
$ python ising.py 
```
<p align="center">
<img align="middle" src="_assets/trg.png" width="500" alt="trg"/>
</p>

### Variational optimization of iPEPS

Run this to optimize an iPEPS wavefuntion for 2D quantum Heisenberg model. Here, we use Corner Transfer Matrix Renormalization Group for contraction, and L-BFGS for optimization. 


```bash
$ cd 2_variational_iPEPS
$ python variational.py -D 3 -chi 30 
```

You can supply the command line argument `-use_checkpoint` to reduce the memory usage. To make use of the GPU, you can add `-cuda <GPUID>`.  You will reach the state-of-the-art variational energy and staggered magnetization using this code. You can also supply your own Hamiltonian of interest. In case of a question, you can type `python variational.py -h`.

<p align="center">
<img align="middle" src="_assets/heisenberg.png" width="500" alt="heisenberg"/>
</p>

### What is under the hood ?

Reverse mode AD computes gradient accurately and efficiently for you! Check the codes in [adlib](https://github.com/wangleiphy/tensorgrad/tree/master/tensornets/adlib) for backward functions which propagate gradients through tensor network contractions. 

### To Cite
```bibtex
@article{Liao2019,
    title={Differentiable Programming Tensor Networks},
    author={Liao, Hai-Jun and Liu, Jin-Guo and Wang, Lei and Xiang, Tao},
    eprint={arXiv:1903.09650},
    url={https://arxiv.org/abs/1903.09650}
}
```

### Explore more
https://github.com/under-Peter/TensorNetworkAD.jl

