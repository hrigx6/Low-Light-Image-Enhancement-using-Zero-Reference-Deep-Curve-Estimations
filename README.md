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

