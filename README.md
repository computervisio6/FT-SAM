# Enhancing Fine-Tuning based Backdoor Defense with Sharpness-Aware Minimization

PyTorch implementation of Enhancing Fine-Tuning based Backdoor Defense with Sharpness-Aware Minimization

## Requirements
see file `requirements.txt` for installing PyTorch environment.

## Datasets and state-of-the-art backdoor attack and defense methods.
The structure of this repository is totally based on [BackdoorBench](https://github.com/SCLBD/BackdoorBench). We also follow [BackdoorBench](https://github.com/SCLBD/BackdoorBench) on the implementation of SOTA attack and defense methods. For the implementation details of SOTA attacks and defenses, please refer to [BackdoorBench](https://github.com/SCLBD/BackdoorBench) for help. 

We test our method on CIFAR-10, Tiny ImageNet and GTSRB datasets.
For CIFAR-10, the dataset will be download automatically. 

## Training
At first, you should run the attack files to generate a backdoored model. We provide an example to run BadNets on CIFAR-10 dataset.
```
cd attack/
python badnet.py --save_folder_name cifar10_preactresnet18_badnet_0_1 --dataset cifar10
```
Feel free to change the hyperparameters to adapt to your desired settings.

## Testing
```
cd ../
python defense/ft-sam.py  --rho 2.0 --save_path test --result_file cifar10_preactresnet18_badnet_0_1 --dataset cifar10 --yaml_path ./config/defense/ft-sam/cifar10.yaml
```


## Acknowledgment
Our project references the codes in the following repos.
- [BackdoorBench](https://github.com/SCLBD/BackdoorBench)
- [SAM](https://github.com/davda54/sam)