# AI 化学实践：项目五

本仓库用于保存 AI 化学实践课程项目的实验 notebook、数据、图片、结果和报告文件。项目使用 Python、Jupyter、PyTorch、Scikit-learn、OpenCV 及 Cellpose 等工具，建议在 Windows、Linux 或 WSL 环境中运行。

## 环境配置

### 运行要求

- Python `3.13` 或更高版本（仓库通过 `.python-version` 指定版本）
- 建议使用 CUDA GPU 运行深度学习和 Cellpose；没有 GPU 时可使用 CPU
- 运行 notebook 需要 Jupyter Notebook 或 JupyterLab

### 使用 uv 配置

仓库提供 `pyproject.toml` 和 `uv.lock`，推荐使用 uv 创建可复现环境：

```bash
uv sync
uv run python -m ipykernel install --user --name p5 --display-name "Python (p5)"
uv run jupyter lab
```

启动 Jupyter 后，在 notebook 的内核选择菜单中选择 `Python (p5)`。

### 使用 Python venv 配置

如果不使用 uv，也可以创建标准 Python 虚拟环境：

```bash
python -m venv .venv
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
# Linux/macOS
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install numpy pandas matplotlib scipy scikit-learn pillow opencv-python cellpose medmnist torch torchvision torchaudio tqdm jupyter ipykernel
jupyter lab
```

当前仓库主要依赖由 `pyproject.toml` 管理。若环境中没有安装 notebook 代码使用的扩展包，可补充安装：

```bash
python -m pip install numpy pandas matplotlib scipy scikit-learn pillow opencv-python cellpose medmnist torch torchvision torchaudio tqdm jupyter ipykernel
```

Windows PowerShell 中如果禁止执行虚拟环境脚本，可先执行：

```powershell
Set-ExecutionPolicy -Scope Process Bypass
```

### 验证环境

```bash
python -c "import torch, numpy, pandas, matplotlib, scipy, sklearn; print('environment ok'); print('CUDA:', torch.cuda.is_available())"
```

首次使用某些数据集或模型时，程序可能需要下载数据或模型文件。请确保网络可用，并将大型数据文件放在仓库规定的数据目录中。

## 仓库结构

### 根目录文件

| 文件 | 说明 |
|---|---|
| `README.md` | 仓库使用说明、环境配置和文件索引。 |
| `pyproject.toml` | Python 项目元信息、Python 版本要求和直接依赖。 |
| `uv.lock` | uv 生成的锁定依赖版本，用于复现环境。 |
| `.python-version` | 项目推荐使用的 Python 版本。 |
| `.gitignore` | Git 忽略规则。 |
| `lab1_ML4ImgRec.ipynb` | Lab1 实验 notebook。 |
| `lab2plus_intro2DL.ipynb` | 深度学习相关补充 notebook。 |
| `lab2_MLP_CNN.ipynb` | Lab2 实验 notebook。 |
| `lab3_intro2CellSeg.ipynb` | Lab3 实验 notebook。 |
| `lab4_Cellpose_GEVI_v3_key.ipynb` | Lab4 实验 notebook，包含批处理和结果汇总代码。 |

