# Low-Light-Image-Enhancement-using-Zero-Reference-Deep-Curve-Estimations
Enhances low-light images and video using Zero-Reference Deep Curve Estimation (Zero-DCE). A lightweight CNN estimates pixel-wise curves for dynamic range adjustment without reference images, using non-reference loss functions to improve brightness, preserve detail, and reduce color distortion.

# Zero-DCE Low-Light Image Enhancement

This project implements **Zero-Reference Deep Curve Estimation (Zero-DCE)** for enhancing low-light images and videos without paired or reference data. A lightweight CNN estimates pixel-wise curves to improve illumination while preserving color consistency and image details.

---

## Requirements

- Python 3.x  
- PyTorch  
- OpenCV  
- NumPy  
- Matplotlib  

Install dependencies as needed using `pip`.

---

## Training the Model

Use `train_model.py` to train the Zero-DCE model on a dataset of low-light images.

### Arguments
- `--dataset_dir` : Path to training dataset (required)
- `--checkpoint_dir` : Directory to save checkpoints
- `--model_type` : Model variant
- `--IMG_H`, `--IMG_W`, `--IMG_C` : Image height, width, and channels
- `--batch_size` : Training batch size
- `--epoch` : Number of epochs
- `--learning_rate` : Learning rate
- `--dataset_split` : Train/validation split
- `--logdir` : Logging directory
- `--filters` : Number of convolution filters
- `--iteration` : Curve iteration count

### Example
```bash
python train_model.py --dataset_dir ./data --epoch 100 --batch_size 8


Testing the Model

Use test_model.py to evaluate a trained model on a dataset.

Arguments

--model_path : Path to trained model (required)

--dataset_path : Path to test dataset

--img_h, --img_w : Image dimensions

--save_plot : Save output comparison plots

--load_random_data : Test on random samples

Example
python test_model.py --model_path ./checkpoints/model.pth --dataset_path ./test_data

Single Image Enhancement

Use single_image_enhance.py to enhance a single low-light image.

Arguments

--model_path : Path to trained model (required)

--image_path : Path to input image (required)

--img_h, --img_w : Image dimensions

--plot : Display the enhanced result

--save_result : Save the enhanced image

--iteration : Curve iteration count

Example
python single_image_enhance.py --model_path model.pth --image_path input.jpg --save_result True

Notes

No paired or reference images are required for training.

Uses non-reference loss functions such as exposure control, spatial consistency, color constancy, and illumination smoothness.

Supports enhancement for both images and video frames.

Reference

Zero-Reference Deep Curve Estimation for Low-Light Image Enhancement
Chunle Guo et al.
