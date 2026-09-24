# 实验一：计算机视觉库的安装

## 一、实验目的

掌握 Anaconda 的安装与基本操作，熟悉 GPU 使用环境的配置及对应版本 PyTorch 的安装，并完成 OpenCV 的安装与配置。

## 二、实验内容

### 1. Anaconda 的安装及配置

- 安装 Anaconda，并配置系统环境变量。
- 验证安装：在终端输入 `conda --version` 查看版本。
- 查看配置：输入 `conda config --show` 查看当前 Conda 配置信息。
- 解决 PowerShell 脚本权限问题，执行 `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` 和 `conda init`。

### 2. Conda 的基本操作与 OpenCV 的安装

- 创建虚拟环境：`conda create --name pytorch_env python=3.10`。
- 激活环境：`conda activate pytorch_env`。
- 安装 OpenCV：`pip install opencv-python -i https://pypi.tuna.tsinghua.edu.cn/simple`。

### 3. GPU 加速环境配置

- 执行 `nvidia-smi` 查看显卡状态。
- **注意**：由于本机仅配备 Intel 核显，无 NVIDIA 独立显卡，因此无法使用 CUDA 加速。本实验后续采用 CPU 版本 PyTorch 进行配置。

### 4. PyTorch 安装

- 由于无 N 卡，直接安装 CPU 版本：`pip install torch torchvision torchaudio -i https://pypi.tuna.tsinghua.edu.cn/simple`。
- 验证安装：进入 Python 环境，输入 `import torch` 和 `print(torch.__version__)`，输出 `2.14.0+cpu`。

### 5. PyTorch GPU 加速环境验证

- 验证 CUDA 是否可用：`print(torch.cuda.is_available())`，输出 `False`。
- 验证 cuDNN 是否可用：`print(torch.backends.cudnn.is_available())`，输出 `False`。
- **结论**：由于硬件限制，GPU 加速不可用，但 PyTorch CPU 版本安装成功，环境配置正确。

## 三、实验结果
<img width="745" height="677" alt="c6f3a0268bb8b8c9717fff6cc5c78d7" src="https://github.com/user-attachments/assets/97e11189-45b2-430d-b23b-410eec43714c" />
<img width="715" height="322" alt="67406bc90529f725be8e3d486a6fdf5" src="https://github.com/user-attachments/assets/29ec8c48-64ab-44f0-b5d1-2e548fef7ead" />
<img width="948" height="652" alt="f5db10ede76a6cccba6639961844ced" src="https://github.com/user-attachments/assets/09994e64-c2ae-40ca-ad90-adc6da914fdd" />
<img width="1814" height="927" alt="d9772fb94357f6b09a614716fd8839d" src="https://github.com/user-attachments/assets/89ec4f13-be04-4b9b-ab79-b2be84e63985" />
<img width="628" height="234" alt="7f840a86759b314acee08042911ad2b" src="https://github.com/user-attachments/assets/1ea4f5cc-55ef-4710-bb6b-1ea702301a40" />
<img width="1797" height="397" alt="47bd4a8a6cf042ffd04d4b0ddf03b10" src="https://github.com/user-attachments/assets/89f0351c-8665-4e9c-a781-2ca62858bc7e" />







### 1. Anaconda 版本与配置

```text
(base) PS C:\Users\lenovo> conda --version
conda 26.1.1
(base) PS C:\Users\lenovo> conda config --show
add_anaconda_token: True
add_pip_as_python_dependency: True
...
