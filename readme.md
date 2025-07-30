# Performance Test

- GPU : Nvidia 3090 24GB
- CPU : Core i 14900K
- RAM : 192 GB
- SSD : SAMSUNG EVO 990

### we trained all models during 10 epochs

| model         | dataset           | pytorch(s) | xtorch(s) |
|---------------|-------------------|------------|-----------|
| Lenet5        | MNIST             | 38.89      | 5.53      |
|               | Fashion MNIST     | 36.38      | 5.22      |
|               | CIFAR10           | 32.71      | 7.81      |
|               | CIFAR100          | 31.99      | 4.52      |
|               | Imagenette        | 28.68      | 1.85      |
|               | Food101           | 819.81     | 275.52    |
| AlexNet       | MNIST             | 287.93     | 192.70    |
|               | Fashion MNIST     | 273.77     | 195.87    |
|               | CIFAR10           | 299.88     | 173.50    |
|               | CIFAR100          | 333.88     | 166.43    |
|               | Imagenette        | 93.23      | 34.30     |
|               | Food101           | 1584.05    |           |
| VGGNet16      | MNIST             | 3099.31    |           |
|               | Fashion MNIST     | 3019.44    |           |
|               | CIFAR10           | 2597.76    |           |
|               | CIFAR100          | 2536.00    |           |
|               | Imagenette        | 447.15     |           |
|               | Food101           | 3794.44    |           |
| ResNet18      | MNIST             | 852.04     |           |
|               | Fashion MNIST     | 824.95     |           |
|               | CIFAR10           | 748.90     |           |
|               | CIFAR100          | 694.50     |           |
|               | Imagenette        | 134.17     |           |
|               | Food101           | 1882.34    |           |



