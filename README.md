# SNN_based_Object_Detection

SNN Based Object Detection implements energy-efficient object classification using Spiking Neural Networks (SNNs) on a subset of the MS COCO dataset. The project uses a ResNet-based spiking model, optimized and deployed on FPGA hardware for real-time edge AI applications.

 Project Overview
This project explores the use of Spiking Neural Networks (SNNs) for object classification, targeting low-power, real-time inference on edge devices. By leveraging the sparse, event-driven nature of SNNs and the hardware efficiency of FPGAs, it demonstrates a pathway for practical, energy-aware AI solutions in vision tasks[1].

 Features
- SNN Model: Modified ResNet18 backbone converted to SNN using SpikingJelly, supporting temporal dynamics and event-driven computation.
- Dataset: Adapted MS COCO subset for classification (5 classes, grayscale, 32x32 images).
- Training Pipeline: PyTorch-based, with surrogate gradient training and spiking state resets.
- FPGA Deployment: Model exported to ONNX, quantized, and synthesized for Xilinx Artix-7 FPGA using hls4ml.
- Optimization: Post-training quantization and model simplification for efficient edge deployment.

 Installation
1. Clone the repository
2. Install dependencies
   - Python 3.8+
   - PyTorch
   - SpikingJelly
   - torchvision
   - onnx, onnxsim, onnxruntime
   - hls4ml
   - numpy, matplotlib

pip install torch torchvision spikingjelly onnx onnxsim onnxruntime hls4ml numpy matplot

 Dataset Preparation
- Download the MS COCO dataset and place a subset of images and the annotation file as specified.
- The project uses a reduced set of 5 classes and downsized images (32x32, grayscale) for efficient SNN training.

 Training
- Configure training parameters in `train.py`.
- Run the training script:

python src/train.py
  
 Model Export and FPGA Deployment
- Export the trained model to ONNX:

python src/export_onnx.py

- Quantize and simplify the ONNX model using ONNX Runtime and onnxsim.
- Use hls4ml to synthesize the quantized model for FPGA deployment.

 Citation

If you use this work, please cite:
> More Prasad Prabhakarrao, Rounak Agrawal, Rounish Chandra, Saket Ranjan. "SNN Based Object Detection." IIIT Dharwad, 2025.


 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

 Acknowledgements
- Dr. Jagadish D N (Project Supervisor)
- SpikingJelly, hls4ml, and PyTorch communities

  
