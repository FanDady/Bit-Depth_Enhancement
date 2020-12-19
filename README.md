# Bit-Depth Enhancement(Pytorch Code)
Restore the low bit-depth images back to the high bit-depth images

The neural network is based on the UNet network

## Introduction
The task of bit depth enhancement is to recover the significant bits lost by quantization. It has important applications in high bit depth display and photo editing. Although most displays are 8-bit, many TVs and smartphones (such as Samsung Galaxy S10 and iPhone x) already support 10 bit displays to meet high dynamic range standards due to growing consumer demand for finer hue values. However, these displays are not fully utilized because most of the available image and video content is still 8-bit. If the 8-bit data is directly stretched on the 10 bit display, there will be obvious contour artifacts, color distortion and detail loss. Therefore, it is of great significance to study bit depth enhancement.

## Requirement
- Environment : Python 3.7(or higher edition)
- DeepLearning Framework: Pytorch 1.4.0 and torchvision 0.4.0
- NVIDIA Turing GPU is strongly recommended 
- Linux/Windows operating system
- A machine with a 4-core processor and 8GB memory (or higher configuration)
- A GPU with 4GB memory minimum
- Keep the batch-size of 2(or higher) and train images cropped to 256x256

## Train
In the code, we use the MITAdobe FiveK as the dataset.And, the fiveK images are divided into training data and validation data.Then,the training data are cropped to 256x256 and the validation data are cropped to 512x512(if the size of images is too large,it will consume a lot of memory of GPU so that the machine may report RuntimeError:CUDA out of memory).Before run the training.py,please change the args such as,batch_size,model_dir,train_dir,test_dir,label_dir
![QQ截图20201219162906](https://user-images.githubusercontent.com/52614278/102684910-7b955f80-4217-11eb-8e3f-819c11d6f8f9.png)

## Test
After training,save the checkpoint.tar file which contains the model parameter and variables.What's more,test data are also needed.In the code, Sintel datasets are downloaded as the test data
