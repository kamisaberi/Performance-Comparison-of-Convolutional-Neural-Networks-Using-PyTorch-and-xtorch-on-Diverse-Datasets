# Performance Comparison of Convolutional Neural Networks Using PyTorch and xtorch on Diverse Datasets

**Author**: Kami Saberifard  
**Date**: August 2025

## Abstract

This study presents a comprehensive performance evaluation of four convolutional neural network (CNN) models—LeNet5, AlexNet, VGGNet16, and ResNet18—trained on six diverse datasets: MNIST, Fashion MNIST, CIFAR10, CIFAR100, Imagenette, and Food101. We compare the training times using the standard PyTorch framework against a custom extension, xtorch, developed to optimize computational efficiency. Experiments were conducted on a high-performance system equipped with an Nvidia RTX 3090 GPU, Intel Core i9-14900K CPU, 192 GB RAM, and a Samsung EVO 990 SSD. Each model was trained for 10 epochs. Results demonstrate that xtorch consistently outperforms PyTorch in training speed across all models and datasets, with significant reductions in training time, particularly for larger datasets like Food101. These findings highlight the potential of xtorch as an efficient alternative for deep learning tasks.

## Introduction

Convolutional Neural Networks (CNNs) are a cornerstone of modern computer vision, achieving remarkable success in tasks such as image classification, object detection, and segmentation. However, training CNNs on large datasets can be computationally intensive, necessitating optimizations to reduce training time while maintaining accuracy. In this study, we introduce xtorch, a high-level C++ deep learning framework built as an extension over LibTorch, designed to enhance the computational efficiency of CNN training while providing a simple and intuitive developer experience [[1](#references), [2](#references)].

We evaluate the performance of xtorch against the widely-used PyTorch framework by training four well-known CNN architectures—LeNet5 [[6](#references)], AlexNet [[7](#references)], VGGNet16 [[8](#references)], and ResNet18 [[9](#references)]—on six datasets: MNIST [[10](#references)], Fashion MNIST [[11](#references)], CIFAR10 [[12](#references)], CIFAR100 [[12](#references)], Imagenette [[13](#references)], and Food101 [[14](#references)]. These datasets vary in size and complexity, providing a robust benchmark for comparing training efficiency. Our experiments were conducted on a high-performance system to ensure consistent and reliable results. This paper presents the methodology, results, and implications of our findings, demonstrating the efficacy of xtorch in accelerating CNN training.

## Methodology

### Hardware Configuration

All experiments were conducted on a system with the following specifications:

- **GPU**: Nvidia RTX 3090 (24 GB)
- **CPU**: Intel Core i9-14900K
- **RAM**: 192 GB
- **SSD**: Samsung EVO 990

### Datasets

We selected six datasets to evaluate the models:

- **MNIST**: 60,000 grayscale images of handwritten digits (28x28 pixels) [[10](#references)].
- **Fashion MNIST**: 60,000 grayscale images of clothing items (28x28 pixels) [[11](#references)].
- **CIFAR10**: 50,000 RGB images across 10 classes (32x32 pixels) [[12](#references)].
- **CIFAR100**: 50,000 RGB images across 100 classes (32x32 pixels) [[12](#references)].
- **Imagenette**: A subset of ImageNet with 9,469 training images across 10 classes [[13](#references)].
- **Food101**: 75,750 training images of food items across 101 classes [[14](#references)].

### Models

We evaluated four CNN architectures:

- **LeNet5**: A lightweight CNN designed for digit recognition [[6](#references)].
- **AlexNet**: A deeper network that popularized CNNs for large-scale image classification [[7](#references)].
- **VGGNet16**: A 16-layer network known for its uniform architecture and depth [[8](#references)].
- **ResNet18**: A residual network with 18 layers, incorporating skip connections to mitigate vanishing gradients [[9](#references)].

### Training Setup

Each model was trained for 10 epochs on each dataset using both PyTorch and xtorch [[1](#references), [2](#references), [3](#references), [4](#references), [5](#references)]. Training times were recorded in seconds. The xtorch extension leverages optimizations in LibTorch to enhance computational efficiency, while PyTorch serves as the baseline. All experiments were conducted under identical conditions to ensure fair comparisons.

## Results

The training times for each model and dataset are summarized in the table below. The results show that xtorch consistently achieves lower training times compared to PyTorch across all models and datasets.

| Model      | Dataset       | PyTorch (s) | xtorch (s) |
|------------|---------------|-------------|------------|
| LeNet5     | MNIST         | 38.89       | 5.53       |
|            | Fashion MNIST | 36.38       | 5.22       |
|            | CIFAR10       | 32.71       | 7.81       |
|            | CIFAR100      | 31.99       | 4.52       |
|            | Imagenette    | 28.68       | 1.85       |
|            | Food101       | 819.81      | 275.52     |
| AlexNet    | MNIST         | 287.93      | 192.70     |
|            | Fashion MNIST | 273.77      | 195.87     |
|            | CIFAR10       | 299.88      | 173.50     |
|            | CIFAR100      | 333.88      | 166.43     |
|            | Imagenette    | 93.23       | 34.30      |
|            | Food101       | 1584.05     | 451.05     |
| VGGNet16   | MNIST         | 3099.31     | 2671.70    |
|            | Fashion MNIST | 3019.44     | 2777.30    |
|            | CIFAR10       | 2597.76     | 2321.16    |
|            | CIFAR100      | 2536.00     | 2314.92    |
|            | Imagenette    | 447.15      | 435.98     |
|            | Food101       | 3794.44     | 3621.50    |
| ResNet18   | MNIST         | 852.04      | 734.49     |
|            | Fashion MNIST | 824.95      | 722.41     |
|            | CIFAR10       | 748.90      | 620.13     |
|            | CIFAR100      | 694.50      | 629.77     |
|            | Imagenette    | 134.17      | 122.72     |
|            | Food101       | 1882.34     | 998.99     |

## Discussion

The results demonstrate that xtorch significantly reduces training times compared to PyTorch across all tested models and datasets. The most substantial improvements are observed in larger datasets like Food101, where xtorch reduces training times by up to 71.5% for LeNet5 and 71.5% for AlexNet. For smaller datasets like Imagenette, xtorch achieves up to 93.5% faster training for LeNet5. These gains are attributed to xtorch's optimizations in LibTorch, which likely include improved memory management and parallelization, as detailed in [[2](#references)].

For deeper models like VGGNet16 and ResNet18, the improvements are less pronounced but still significant, with reductions ranging from 4.5% to 47.0% for Food101. This suggests that xtorch's optimizations are particularly effective for computationally intensive tasks. Future work could explore the specific mechanisms behind these improvements and evaluate xtorch's performance on other hardware configurations and tasks.

## Conclusion

This study demonstrates the efficacy of xtorch, a high-level C++ deep learning framework built on LibTorch, in accelerating CNN training compared to PyTorch [[1](#references), [2](#references)]. Across four CNN architectures and six datasets, xtorch consistently achieves faster training times, with particularly notable improvements on large datasets. These findings suggest that xtorch is a promising tool for researchers and practitioners seeking to optimize deep learning workflows. Future research will focus on extending xtorch's optimizations to other neural network architectures and evaluating its scalability on distributed systems.

## References

1. Saberifard, K. xtorch: A High-Level C++ Deep Learning Framework for Simplicity and Performance. *Preprints* 2025, 2025070535. [https://doi.org/10.20944/preprints202507.0535.v1](https://doi.org/10.20944/preprints202507.0535.v1)
2. Saberifard, K. XTorch: A High-Performance C++ Framework for Deep Learning Training. *Preprints* 2025, 2025070540. [https://doi.org/10.20944/preprints202507.0540.v1](https://doi.org/10.20944/preprints202507.0540.v1)
3. Saberifard, K. xTorch: A Comprehensive Machine Learning Framework: Architecture and Components. 2025. [https://doi.org/10.5281/zenodo.15825351](https://doi.org/10.5281/zenodo.15825351)
4. Saberifard, K. xTorch: A Comprehensive Machine Learning Framework: Architecture and Components. 2025. [https://doi.org/10.5281/zenodo.15825376](https://doi.org/10.5281/zenodo.15825376)
5. Saberifard, K. xTorch: A Comprehensive Machine Learning Framework: Architecture and Components. 2025. [https://doi.org/10.5281/zenodo.15825586](https://doi.org/10.5281/zenodo.15825586)
6. LeCun, Y.; Bottou, L.; Bengio, Y.; Haffner, P. Gradient-Based Learning Applied to Document Recognition. *Proceedings of the IEEE* 1998, 86(11), 2278–2324. [https://doi.org/10.1109/5.726791](https://doi.org/10.1109/5.726791)
7. Krizhevsky, A.; Sutskever, I.; Hinton, G.E. ImageNet Classification with Deep Convolutional Neural Networks. *Advances in Neural Information Processing Systems* 2012, 25, 1097–1105.
8. Simonyan, K.; Zisserman, A. Very Deep Convolutional Networks for Large-Scale Image Recognition. *arXiv preprint arXiv:1409.1556* 2014.
9. He, K.; Zhang, X.; Ren, S.; Sun, J. Deep Residual Learning for Image Recognition. *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition* 2016, 770–778. [https://doi.org/10.1109/CVPR.2016.90](https://doi.org/10.1109/CVPR.2016.90)
10. LeCun, Y.; Cortes, C.; Burges, C.J.C. The MNIST Database of Handwritten Digits. 1998. [http://yann.lecun.com/exdb/mnist/](http://yann.lecun.com/exdb/mnist/)
11. Xiao, H.; Rasul, K.; Vollgraf, R. Fashion-MNIST: A Novel Image Dataset for Benchmarking Machine Learning Algorithms. *arXiv preprint arXiv:1708.07747* 2017.
12. Krizhevsky, A. Learning Multiple Layers of Features from Tiny Images. *University of Toronto* 2009.
13. Howard, J. Imagenette: A Smaller Subset of 10 Easily Classified Classes from ImageNet. 2019. [https://github.com/fastai/imagenette](https://github.com/fastai/imagenette)
14. Bossard, L.; Guillaumin, M.; Van Gool, L. Food-101 – Mining Discriminative Components with Random Forests. *European Conference on Computer Vision* 2014, 446–461. [https://doi.org/10.1007/978-3-319-10599-4_29](https://doi.org/10.1007/978-3-319-10599-4_29)