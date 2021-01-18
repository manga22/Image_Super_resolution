# Image_Super_resolution

Modify the config file to set all paths and model parameters

Config file: config/config.ini


## To train the model

python train.py --config=config/config.ini --model_path=models/upscale2x.h5 --epochs=300

## To test the model on a given image

python test.py --model_path=models/upscale2x.h5 --test_image_path=data/test/baby.png

## To evaluate PSNR metric on test dataset 

e.g., python eval.py --model_path=models/upscale2x_noise4.h5 --test_dir=data/test --noise_level=4
