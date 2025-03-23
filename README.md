
## Installation
Clone the repository
```bash
git clone https://github.com/neil-tan/peft_gr00t.git
cd peft_gr00t
git submodule update --init --recursive
```
Install the dependencies
```bash
conda create -n gr00t python=3.10
conda activate gr00t
pip install --upgrade setuptools
pip install -e Isaac-GR00T
pip install --no-build-isolation flash-attn==2.7.1.post4 
```

## Dataset
Dataset https://huggingface.co/datasets/ChillyMango/sort-red-blocks-medium


## Training
Running the PEFT training script
```bash
python gr00t_petf_finetune.py --dataset-path ./Isaac-GR00T/demo_data/robot_sim.PickNPlace --num-gpus 1 --lora_rank=16

```