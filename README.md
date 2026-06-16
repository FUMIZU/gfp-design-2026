# gfp-design-2026
SynBio Challenges 2026 GFP protein design submission

本项目为 2026 年 SynBio Challenges GFP 设计赛题的提交方案，采用基于文献验证的突变模块组合策略，辅以 ProteinMPNN 结构生成，使用 ESM-1v 蛋白质语言模型作为特征提取和稳定性评估工具，共分为环境搭建与数据就位、候选序列生成、特征提取与亮度模型训练、评分过滤与终选、输出与提交五个阶段。

GFP设计竞赛项目需要Python 3.8或更高版本（本次使用的版本为3.11）

核心依赖包包括：

fair-esm（用于加载ESM蛋白质语言模型如esm1v_t33_650M_UR90S，提取突变体序列的嵌入向量作为荧光强度预测的特征输入）

transformers（作为HuggingFace模型接口，备选加载ESM或其他蛋白质语言模型）

xgboost（训练梯度提升树回归模型，根据ESM特征预测GFP突变体的亮度值）

scikit-learn（提供数据预处理、标准化、模型评估指标计算如R²和交叉验证功能）

pandas（读取Excel格式的训练数据、处理突变信息表和排除列表CSV、保存候选序列及生成提交文件）

numpy（存储嵌入向量数组、执行矩阵运算和数值转换）

biopython（处理FASTA格式的野生型序列文件、验证氨基酸序列合法性）

安装命令为：pip install fair-esm transformers xgboost scikit-learn pandas numpy biopython


目录结构：
├── README.md              # 项目说明和复现指引

├── requirements.txt       # Python依赖清单和版本号

├── notebooks/             # Colab笔记本归档

│   ├── 01_environment_setup.ipynb

│   ├── 02_candidate_generation.ipynb

│   ├── 03_feature_extraction.ipynb

│   ├── 04_screening_and_selection.ipynb

│   └── 05_final_check.ipynb

├── output/                # 最终提交物和中间文件样本

│   └── submission_template.csv

└── docs/                  # 设计说明文档和辅助材料

    └── design_documentation.pdf

    
