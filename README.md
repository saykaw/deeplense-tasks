## Common Task 1

| **Model** | **AUC (no)** | **AUC (sphere)** | **AUC (vort)** | **AUC (Overall)** |
|-----------|--------------|------------------|----------------|-------------------|
| ViT       | 0.985        | 0.964            | 0.981          | 0.977             |
| ResNet    | 0.995        | 0.992            | 0.997          | 0.995             |

## Supervised Approach for Specific Test Task 3 (EDSR)
## Task 3A: Training an EDSR

| Stage      | MSE    | SSIM   | PSNR   |
|------------|--------|--------|--------|
| Test       | 0.0001 | 0.9759 | 42.3159|

## Task 3B: Finetuning EDSR 
(refer code for stages description)

| Stage       | MSE    | SSIM   | PSNR   |
|-------------|--------|--------|--------|
| Test_Stage1 | 0.0016 | 0.8064 | 27.9314|
| Test_Stage2 | 0.0015 | 0.8028 | 28.1744|
| Test_Stage3 | 0.0010 | 0.8027 | 29.7925|
| Test_Stage4 | 0.0011 | 0.8064 | 29.7422|
| Test_Stage5 | 0.0011 | 0.7889 | 29.4955|

The best model is the **Stage3**, with a PSNR of 29.7925, SSIM of 0.8027 and MSE of 0.0010. It is saved as `edsr_finetuned_best_Stage3.pth`.

## Unsupervised Approach for Specific Test Task 3 (CycleGAN)
## Task 3A: Training a CycleGAN

| **Model**         | **PSNR** | **SSIM** | **MSE**  | **FID**  |
|-------------------|----------|----------|----------|----------|
| Vanilla CycleGAN  | 35.28    | 0.9322   | 0.0003   | 11.30    |
| Physics CycleGAN  | 35.45    | 0.9415   | 0.0003   | 73.06    |

The best model is the **Vanilla CycleGAN**, with a PSNR of 35.28, SSIM of 0.9322, MSE of 0.0003, and the lowest FID of 11.30. It is saved as `cyclegan_epoch15.pth`.

## Task 3B: Finetuning a CycleGAN

| **Epochs** | **PSNR** | **SSIM** | **MSE**  | **FID**  |
|------------|----------|----------|----------|----------|
| 5          | 31.33    | 0.8751   | 0.0007   | 81.22    |
| 10         | 31.11    | 0.8711   | 0.0008   | 53.72    |
| 20         | 29.12    | 0.7947   | 0.0012   | 72.25    |

The best model is the one fine-tuned for **5 epochs**, with the highest PSNR (31.33), highest SSIM (0.8751), and lowest MSE (0.0007). It is saved as `cyclegan_finetuned_epoch5.pth`.
