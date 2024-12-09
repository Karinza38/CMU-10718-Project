# CMU 10718 Project 

This repo is adapted from SimVQ repo -- https://github.com/youngsheen/SimVQ. 
Thanks to https://github.com/lucidrains/vector-quantize-pytorch, it provides a concise implementation for most VQ methods has saved me a lot of trouble.

## Prepare


Dependencies: `pip install -r requirements.txt`


```python
Datasets
imagenet
└── train/
    ├── n01440764
        ├── n01440764_10026.JPEG
        ├── n01440764_10027.JPEG
        ├── ...
    ├── n01443537
    ├── ...
└── val/
    ├── ...


```

## Scripts


### Training

- Image Tokenizer Training
`XDG_CACHE_HOME="dataset/ILSVRC2012" python main.py fit --config /home/hengl/vq/OurVQ/configs/imagenet_our_128_B.yaml`


### Evaluating 


- Image Tokenizer Evaluation

`XDG_CACHE_HOME="dataset/ILSVRC2012" python evaluation.py --config_file vq_log/our_262k/size128/config.yaml --ckpt_path vq_log/our_262k/1.ckpt`


### Note that 

The major implementation of LRM-VQ can be seen at `taming/modules/vqvae/lrm_vq.py`. You should see the depth control the linears of matrixs in codebook_transformation. 
