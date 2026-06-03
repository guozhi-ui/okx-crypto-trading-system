# OKX加密货币自动交易系统

**作者**：guozhicheng  
**学号**：1305996

## 研究问题

如何使用OKX Open API和Python设计一个稳定的自动交易系统，并评估结合EMA21/EMA50、RSI和布林带的多指标策略在BTC/USDT 15分钟市场中是否优于单指标策略？

## 数据集概述

本数据集包含OKX交易所BTC/USDT交易对的15分钟OHLCV数据，以及预计算的技术指标（EMA、RSI、布林带）。

- **数据来源**：OKX Open API V5（`https://www.okx.com/docs-v5/en/`）
- **收集时间范围**：2026-04-10 00:00:00 至 2026-05-10 23:59:59（30天）
- **总观测数**：2830行
- **收集方法**：使用Python的ccxt库自动调用API

## 项目结构

```
okx-crypto-trading-system/
├── .env                    # API密钥配置文件（已添加到.gitignore，不会上传）
├── .gitignore             # Git忽略文件配置
├── README.md              # 项目说明文档
├── data/                  # 数据文件夹
│   └── btc_usdt_15m_data.csv
├── code/                  # 代码文件夹
│   └── data_collection.ipynb
└── docs/                  # 文档文件夹
    └── data_description.md
```

## 运行数据收集Notebook的方法

### 前置条件

1. 安装Python 3.9+
2. 拥有OKX账号并创建API密钥（开启模拟交易模式）
3. 安装所需依赖：
   ```bash
   pip install ccxt pandas ta python-dotenv jupyter
   ```

### 运行步骤

1. 克隆本仓库到本地
2. 在根目录创建`.env`文件，填入你的OKX API信息：
   ```env
   OKX_API_KEY=你的API Key
   OKX_API_SECRET=你的Secret Key
   OKX_PASSPHRASE=你的API密码
   OKX_DEMO_MODE=True
   ```
3. 启动Jupyter Notebook：
   ```bash
   jupyter notebook
   ```
4. 打开`code/data_collection.ipynb`，按顺序运行所有单元格

### 注意事项

- 数据集将保存到`data/btc_usdt_15m_data.csv`
- 本仓库仅包含数据集样本，完整数据集可联系作者获取
- **重要**：`.env`文件包含敏感信息，已添加到`.gitignore`，不会被提交到GitHub

## 技术栈

- **Python 3.9+**：主要编程语言
- **ccxt**：加密货币交易所统一API接口
- **pandas**：数据处理和分析
- **ta-lib (ta)**：技术指标计算
- **python-dotenv**：环境变量管理
- **Jupyter Notebook**：交互式开发环境

## 许可证

本项目仅供学习和研究使用。
