# Repository containing the code base for training the multi-agent coordination policy used in the paper."Decentralized Multi-robot Path Planning using Graph Neural Networks"



## Setup
Clone with `git clone --recursive` to include submodules. Run `./build.sh` to set up a docker container for training. Training can be performed without docker by installing all requirements in the host system according to the `Dockerfile`.

## Train
Start training by running
```
./run.sh python3 src/train.py
```
The training will stop automatically after 5000 training iterations.

## Evaluate
Optionally, evaluate the policy performance by running
```
./run.sh python3 src/evaluate.py results/MultiPPO_simple_xxxx/checkpoint_yyyyyy
```
where the path to the model checkpoint has to be adapted accordingly.



```
./run.sh python3 src/export.py results/MultiPPO_simple_xxxx/checkpoint_yyyyyy
```
The exported torchscript model will be saved in the same checkpoint folder and can then manually be copied to the correct location in the ROS2 project.
