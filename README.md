# Image_Super_resolution

Modify the config file to set all paths and model parameters

#Config file: config/config.ini


#To train the model

python train.py --config=config/config.ini --model_path=models/upscale2x_model.h5 --epochs=30 


#To test the model on a given image
python test.py --model_path=models/upscale2x_model.h5 --test_image_path=data/test/butterfly.png
