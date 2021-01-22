# Image_Super_resolution

Required libraries: tensorflow-2.4.0, skimage, opencv, matplotlib

### Prepare config file for training and testing
Prepare the config file to set paths and model parameters for model training and save in 'config' folder

```
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

```python train.py --config=path/to/config.ini --model_path=/path/to/save/model --epochs=200```

## To test the model on a given image

```python test.py --model_path=path/to/model --test_image_path=path/to/test_image```

Example:
```python test.py --model_path=models/upscale2x.h5 --test_image_path=data/test/baby.png```

## To evaluate PSNR metric on test dataset 

```python test.py --model_path=path/to/model --test_dir=path/to/test/directory --noise_level=k```

Example:
```python eval.py --model_path=models/upscale2x_noise4.h5 --test_dir=data/test --noise_level=4```
