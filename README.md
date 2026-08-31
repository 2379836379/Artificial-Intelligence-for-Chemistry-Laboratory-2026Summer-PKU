# AI 化学实践：项目五

项目地址：[https://github.com/2379836379/Artificial-Intelligence-for-Chemistry-Laboratory-2026Summer-PKU](https://github.com/2379836379/Artificial-Intelligence-for-Chemistry-Laboratory-2026Summer-PKU)

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

