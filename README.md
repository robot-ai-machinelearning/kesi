# Gift from Iterative Network Pruning 
This repository contains the code for reproducing the results, and trained ImageNet models for paper [Paying more attention to Snapshot of Iterative Pruning: Improving Model Compression via Ensemble Distillation](https://arxiv.org/pdf/2006.11487.pdf).

## Summary

In short, the paper propose to leverage the snapshots of iterative pruning to construct ensembles and distilling knowledge from them. To stimulate the diversity between each snapshots, we use *One-cycle schedule* to retrain the pruned networks. Thus, each snapshot is encouraged to converge to different optimal solution.

The algorithm is summarized below:

1. **Train** the baseline network to completion.
2. **Prune** redundant weights (based on some criteria).
3. **Retrain** with *One-cycle learning rate*.
4. **Repeat** step 2 and 3 until desired compression ratio is reached.
5. **Distill** knowledge from ensemble to desired network.

## How to run

Please checkout `example.pynb` for detail instruction for reproducing the results

## Results

### CIFAR-10 and CIFAR-100. 

![Results on CIFAR](assets/results.png)

### Tiny-Imagenet 

![Results on Tiny-Imagenet](assets/tinyimagenet.png)



**PFEC** and **MWP** stand for [Pruning Filters for Efficient ConvNets](https://arxiv.org/abs/1608.08710) and [Learning both Weights and Connections for Efficient Neural Networks](https://arxiv.org/abs/1506.02626) respectively.

## Acknowledgement 
The code is mostly taken from [Eric-mingjie's repository](https://github.com/Eric-mingjie/rethinking-network-pruning)
