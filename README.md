# 抗高血压药物剂量-反应分析

一个完整可复现、带版本管理的医药数据分析小项目：针对一款**假想**抗高血压药物的
合成 I 期剂量-反应数据，用 Jupyter Notebook 完成数据加载、描述性统计、线性
剂量-反应模型拟合与可视化。

> **数据说明：** `data/dose_response.csv` 中的患者数据为**合成数据**，仅用于
> 演示与教学，不代表任何真实临床试验结果，不可用于医疗决策。

## 仓库内容

| 路径 | 说明 |
| --- | --- |
| `drug_response_analysis.ipynb` | 主 Jupyter Notebook，包含完整分析与结果 |
| `data/dose_response.csv` | 合成输入数据（剂量 vs. 收缩压下降幅度） |
| `figures/dose_response_curve.png` | Notebook 生成的剂量-反应曲线图 |
| `requirements.txt` | 锁定的 Python 依赖，保证可复现 |
| `.gitignore` | Python / Jupyter 忽略规则 |

## 环境要求

- Python 3.10 及以上
- 依赖包见 `requirements.txt`（numpy、pandas、matplotlib）

## 复现步骤

1. 克隆仓库：

   ```bash
   git clone <仓库地址>
   cd <仓库名>
   ```

2. 创建并激活虚拟环境（推荐）：

   ```bash
   python -m venv .venv
   source .venv/bin/activate        # Linux / macOS
   .venv\Scripts\activate           # Windows
   ```

3. 安装依赖：

   ```bash
   pip install -r requirements.txt
   ```

4. 启动 Jupyter 并打开 Notebook：

   ```bash
   jupyter notebook drug_response_analysis.ipynb
   ```

运行 **Kernel → Restart & Run All** 即可重现全部结果。Notebook 只读取本地
CSV 文件，不依赖网络，因此结果完全可复现。

## 分析内容

Notebook 依次输出：

- 剂量与收缩压下降幅度的描述性统计；
- 最小二乘（OLS）线性剂量-反应模型 `y = 斜率 × 剂量 + 截距`；
- 决定系数 R²，用于衡量拟合优度；
- 观测散点与拟合回归线的对照图。

## 版本管理

本项目使用 Git 进行版本管理，并在稳定版本打有标签：

```bash
git tag          # 查看标签（例如 v1.0.0）
git log --oneline
```

## 许可证

本项目仅供教学与演示用途。
