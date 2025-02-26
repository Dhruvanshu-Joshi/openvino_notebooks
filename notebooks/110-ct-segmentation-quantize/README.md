# Quantize a Segmentation Model and Show Live Inference

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/openvinotoolkit/openvino_notebooks/HEAD?filepath=notebooks%2F110-ct-segmentation-quantize%2F110-ct-scan-live-inference.ipynb)

<p align="center">
    <img src="https://user-images.githubusercontent.com/77325899/154279555-aaa47111-c976-4e77-8d23-aac96f45872f.gif"/>
</p>

## Notebook Contents

This folder contains five notebooks that show how to train,
optimize, quantize and show live inference on a [MONAI](https://monai.io/) segmentation model with
[PyTorch Lightning](https://lightning.ai/) and OpenVINO:

1\. [Data Preparation for 2D Segmentation of 3D Medical Data](data-preparation-ct-scan.ipynb)

2\. [Train a 2D-UNet Medical Imaging Model with PyTorch Lightning](pytorch-monai-training.ipynb)

3a. [Convert and Quantize a UNet Model and Show Live Inference using POT](110-ct-segmentation-quantize.ipynb)

3b. [Convert and Quantize a UNet Model and Show Live Inference using NNCF](110-ct-segmentation-quantize-nncf.ipynb)

4\. [Live Inference and Benchmark CT-scan Data with OpenVINO](110-ct-scan-live-inference.ipynb)

The main difference between the POT and NNCF quantization notebooks is that NNCF performs quantization within the PyTorch framework, while POT performs
quantization after the PyTorch model has been converted to OpenVINO IR format. There is a pre-trained model and a subset of the dataset provided for the quantization notebook, 
so it is not required to run the data preparation and training notebooks before running the quantization tutorial.

This quantization tutorial consists of the following steps:

* Converting an ONNX model to OpenVINO IR with [Model Optimizer](https://docs.openvino.ai/latest/openvino_docs_MO_DG_Deep_Learning_Model_Optimizer_DevGuide.html).
* Quantizing a model with the [Post-Training Optimization Tool](https://docs.openvino.ai/latest/pot_compression_api_README.html) API in OpenVINO.
* Evaluating the F1 score metric of the original model and the quantized model.
* Benchmarking performance of the original model and the quantized model.
* Showing live inference with async API and MULTI plugin in OpenVINO.

You will also see real-time segmentation of kidney CT scans running on a CPU, iGPU, or combining both devices for higher
throughput. The processed frames are 3D scans that are shown as individual slices. The visualization slides through the slices with detected kidneys
overlayed in red. A pre-trained and quantized model is provided, so running the previous notebooks (1-3) in the series is not required.

## Installation Instructions

If you have not installed all required dependencies, follow the [Installation Guide](../../README.md).
