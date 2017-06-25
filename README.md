# Multi-Layer Perceptron for MNIST Classification

This is a minimal example to write a feed-forward net.
The code consists of three parts: dataset preparation, network and optimizer definition and learning loop.
This is a common routine to write a learning process of networks with dataset that is small enough to fit into memory.

If you want to run this example on the N-th GPU, pass `--gpu=N` to the script.

## Examples of how to train only last layer

#### train\_mnist.py (reference)

- chainer's original train\_mnist.py 

#### train\_no\_backprop\_mode.py

- Use `chainer.no_backprop_mode` 
- chainer v2 is required
- You may train with chainer v1 but it won't work properly
- Less training time

#### train\_del\_gradient.py

- Use hook to delete gradients
- It takes as much time as reference 

#### train\_volatile\_on\_without\_evaluator.py

- Manipulate Variable's `volatile` flag
- It won't work with evaluator (Exception is raised)
- Less training time
- chainer 1.x.x is required (`volatile` flag is not supported in chainer v2) 

#### train\_volatile\_on\_with\_evaluator.py
 
- Manipulate Variable's `volatile` flag
- Use custom evaluator
- It works with evaluator
- Less training time
- chainer 1.x.x is required (`volatile` flag is not supported in chainer v2) 

