# Improved-Blue-Noise-for-Diffusion-Models
Tested on IADB-bn from https://github.com/xchhuang/bndm. 
A substantially improved blue noise for IADB models(as compared to the original). Tested on AFHQ-Cat-64 dataset.
![output2](https://github.com/user-attachments/assets/ea93ae56-0d6d-4369-bcf7-4b4d9bc2724c)
to train
```
python iadb_bn.py --dataset=cat_res64 --res=64 --batch_size=32 --epochs=20 --train_or_test=train --lr=0.0001 --grad_clip=1.0  --noise_type=gaussianBN --scheduler_gamma=sigmoid --scheduler_param=1000 --out_channel=6 --cov=bluev21 --model=bluev21
```
to sample
```
python iadb_bn.py --model=model_bluev21 --cov=bluev21 --dataset=cat_res64 --res=64 --batch_size=16 --train_or_test=test --nb_steps=250 --test_samples=5153 --noise_type=gaussianBN --scheduler_gamma=sigmoid --scheduler_param=1000 --out_channel=6
```
replace bluev21 with any covariance matrix of your choice

to test use scores notebook

to generate noise use noiseopt2 notebook


Get our computed Covariance Matrices(L) here:
https://drive.google.com/drive/folders/1V_nsPTkJn6tjL40RsEIOj1W6drOC0Ajp?usp=sharing
