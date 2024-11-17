# electron
This project implements DnCNN (Denoising Convolutional Neural Network) for image denoising using PyTorch. The model is designed to remove noise from images while preserving important details, such as edges and textures, by learning the residual between clean and noisy images. This project was developed as part of the **Image Denoising and Object Recognition Challenge** within the **Electron Hackathon** organized by LSE & ETTI. The challenge aimed to enhance image processing techniques for various computer vision tasks, including denoising and object recognition.

## Features
- **DnCNN Architecture:** A deep convolutional network with multiple layers of convolution, batch normalization, and ReLU activations.
- **Image Denoising:** Trains on noisy images and attempts to recover the clean versions.
- **Evaluation:** Evaluates the model on validation data and computes PSNR (Peak Signal-to-Noise Ratio) for model performance.
- **Checkpointing:** Saves the best and latest model checkpoints based on PSNR performance.
- **TensorBoard Support:** Logs training and evaluation metrics for visualization.

## Usage
### Training
To start training, run the main script:

```bash
python train.py
```

It will automatically load the data, train the model, and log the training and validation metrics to TensorBoard.

### Evaluation
To test PSNR on noisy and original images, use:

```bash
python test.py --path <path_to_images>
```

Arguments:
--path: Path to the noisy and original images for PSNR evaluation.

## File Structure
- train.py           : Training script
- test.py            : Evaluation script
- model/DnCNN.py     : DnCNN model definition
- processing/        : Data processing and loading utilities
- utils/             : Utility functions for metrics and logging
- experiments/       : Stores checkpoints and TensorBoard logs

## Model Architecture
DnCNN: Consists of a series of convolutional layers with ReLU activations and batch normalization. The model is trained to predict the noise and subtract it from the noisy input.

## License
MIT License. See LICENSE file for details.
