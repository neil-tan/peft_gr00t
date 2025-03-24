### instruction
- git clone the dataset
- Create a `modality.json` in the `path/to/dataset/meta` folder
```json
{
    "state": {
        "single_arm": {
            "start": 0,
            "end": 5
        },
        "gripper": {
            "start": 5,
            "end": 6
        }
    },
    "action": {
        "single_arm": {
            "start": 0,
            "end": 5
        },
        "gripper": {
            "start": 5,
            "end": 6
        }
    },
    "video": {
        "phone": {
            "original_key": "observation.images.phone"
        }
    },
    "annotation": {
        "human.task_description": {
            "original_key": "task_index"
        }
    }
}
```
- modify the SO-100 arm setting:
```json
class So100DataConfig(BaseDataConfig):
    # video_keys = ["video.webcam"]
    video_keys = ["video.phone"]
```

# Training
```bash
/home/neil/.pyenv/versions/miniconda-latest/envs/gr00t/bin/python /home/neil/code/finetune/Isaac-GR00T/scripts/gr00t_petf_finetune.py --dataset_path=/home/neil/code/finetune/Isaac-GR00T/hackathon/tmp/sort-red-blocks-medium --num_gpus 1 --data-config so100 --video-backend torchvision_av
```