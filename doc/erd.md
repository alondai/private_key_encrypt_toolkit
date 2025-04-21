# 工程结构和数据结构设计文档（ERD）

## 目录结构
```
project/
│
├── encrypt_csv.py            # 加密 add.csv 的脚本
├── decrypt_utils.py          # 提供解密函数的模块
├── encrypted_add.csv         # 加密后的输出文件
└── doc/                      # 设计文档目录
    ├── prd.md
    ├── erd.md
    └── todolist.md
```

## 数据结构设计

### 加密数据结构（encrypted_add.csv 内容）
该文件为二进制格式（非明文 CSV），包含以下部分：
- salt (16 bytes)
- nonce (12 bytes)
- ciphertext（加密后的 CSV 内容）
- tag（身份认证标签，16 bytes，GCM 自带）

### decrypt_utils 接口设计
```python
def decrypt_csv(file_path: str, password: str) -> pd.DataFrame:
    '''
    解密指定的文件并返回 DataFrame
    '''
```

## 模块设计
1. 加密器模块（encrypt_csv.py）
2. 解密器模块（decrypt_utils.py）
