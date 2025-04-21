# 私钥加密工具集

一个用于安全加密和解密CSV文件的Python工具集,专门设计用于保护包含私钥的CSV文件。

## 📚 功能特点

### 🔒 安全性
- 使用Argon2id进行密钥派生(RFC 9106高内存配置)
- 使用AES-256-GCM进行加密,提供数据完整性验证
- 支持安全删除明文文件
- 所有密码操作使用安全的getpass模块

### 🛠 主要功能
- 加密明文CSV文件(add.csv → encrypted_add.csv)
- 解密加密文件并返回DataFrame数据结构
- 完整的错误处理和用户提示
- 命令行工具支持

## 🚀 快速开始

### 系统要求
- Python 3.6+
- 操作系统: Linux/macOS/Windows

### 安装依赖
```bash
pip install pandas cryptography argon2-cffi
```

### 使用方法

#### 1. 加密CSV文件
```bash
# 基本用法
python encrypt_csv.py

# 加密后删除明文文件
python encrypt_csv.py -d
```

#### 2. 在代码中使用解密功能
```python
from decrypt_utils import decrypt_csv

# 解密文件并获取DataFrame
df = decrypt_csv('encrypted_add.csv', 'your_password')
```

## 📖 详细说明

### 加密过程
1. 读取add.csv文件
2. 安全输入加密密码
3. 生成随机salt和nonce
4. 使用Argon2id派生AES密钥
5. 使用AES-256-GCM加密数据
6. 保存为encrypted_add.csv
7. 可选删除明文文件

### 解密过程
1. 读取加密文件
2. 提取salt和nonce
3. 使用密码派生密钥
4. 解密数据并验证完整性
5. 转换为DataFrame返回

### 文件格式
加密文件(encrypted_add.csv)包含:
- salt (16字节)
- nonce (12字节)
- 密文
- GCM认证标签(16字节)

## ⚠️ 安全说明

### 注意事项
1. 请使用足够强度的密码
2. 密码错误或数据被篡改时会提示错误
3. 建议定期更换加密密码
4. 请安全保管加密密码

### 错误处理
- 文件不存在: FileNotFoundError
- 密码错误: ValueError
- 数据被篡改: ValueError
- 格式错误: ValueError

## 📁 项目结构
```
project/
│
├── encrypt_csv.py            # 加密CSV文件的脚本
├── decrypt_utils.py          # 提供解密功能的模块
├── README.md                 # 本文档
├── CHANGELOG.md             # 更新日志
└── doc/                     # 文档目录
    ├── prd.md              # 产品需求文档
    ├── erd.md              # 工程结构设计
    ├── todolist.md         # 开发任务清单
    └── cursor-log.md       # 开发日志
```

## 📝 开发文档

### 设计文档
- [产品需求文档](doc/prd.md)
- [工程结构设计](doc/erd.md)
- [开发任务清单](doc/todolist.md)
- [开发日志](doc/cursor-log.md)

### 更新日志
详见[CHANGELOG.md](CHANGELOG.md)

## 🔜 未来计划
- 支持YAML/JSON格式
- 密码管理器集成
- 更多加密算法支持

## 📄 许可证
MIT License 