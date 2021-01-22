# Image_Super_resolution

Modify the config file to set paths and model parameters for model training. 

```
#sample config.ini
[train]
upscale_factor = 2            #Prepare data for this scale factor
noise_sigma = 0               #Variance of noise to add to input data
patch_size= 64                #High resolution patch size =64, Low resolution patch size would be patch_size/upscale_factor
stride = 16                   #Stride to extract image patches for training
train_img_dir = data/train    #Path to training data

[test]
upscale_factor = 2            #Prepare test data for evaluation
noise_sigma = 0               #Set same variance used for training
test_img_dir = data/test      #Path to test data
```



## To train the model

```python train.py --config=config/config.ini --model_path=models/upscale2x.h5 --epochs=200```

## To test the model on a given image

```python test.py --model_path=models/upscale2x.h5 --test_image_path=data/test/baby.png```

## To evaluate PSNR metric on test dataset 

```python eval.py --model_path=models/upscale2x_noise4.h5 --test_dir=data/test --noise_level=4```
