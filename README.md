# einiBasketball
It is for the code and dataset for the Re-Identification Algorithm for Multiplayer Players Based on Sliding Window and Weighting-Scoring.

### env setting
```
conda create -n sw2mp python=3.7
conda activate sw2mp
conda install pytorch==1.1.0 torchvision==0.3.0 -c pytorch
```
GPU Memmory >= 10G, Memory >= 20G(LINUX with CUDN)


* Pre-trained Model 
* ([pose_hrnet_w48_256x192.pth](https://pan.baidu.com/s/1u3zXr-kah-TuLuePVBPqoQ?pwd=qb3n), [r50_ibn_a.pth](https://pan.baidu.com/s/1-fF4th4kE9h5zt41SHPgAg?pwd=62sh)) 
* please download it to path ``
r50_ibn_a.pth : core/models/model_reid.py line 71
pose_hrnet_w48_256x192.pth: core/models/model_keypoints/config/default.py line 133
``)

train
```
python main.py --mode train \
--dataset_path /your path to daraset \
--output_path ./results
```

test
```
python main.py --mode test \
--resume_test_path path/to/pretrained/model --resume_test_epoch 119 \
--duke_path path/to/dataset --output_path ./results
```
example
```
python main.py --mode test \
--resume_test_path /root/autodl-tmp/SWWS-Net-master/base/models --resume_test_epoch 119 \
--dataset_path /root/autodl-tmp/dataset/duke --output_path ./exp_on_c
```


A self-made dataset for basketball players  Re-ID.
https://github.com/jiangtaoluo/einiBasketball/releases/tag/Datasets
