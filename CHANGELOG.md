# 更新日志

## v1.0.0 (2024-03-27)

### 🚀 新功能

#### encrypt_csv.py模块
- ✨ 实现CSV文件加密功能
  - 支持从add.csv读取数据
  - 使用getpass实现安全的密码输入
  - 自动生成加密所需的salt和nonce
  - 使用Argon2id进行密钥派生
  - 使用AES-256-GCM进行数据加密
  - 输出为encrypted_add.csv
  - 支持可选删除明文文件

#### decrypt_utils.py模块
- ✨ 实现CSV文件解密功能
  - 提供decrypt_csv函数用于解密
  - 支持读取加密文件中的salt和nonce
  - 使用相同的密钥派生和解密算法
  - 将解密数据转换回DataFrame
  - 提供完整的异常处理机制

### 🛠 修复与优化

#### 安全性优化
- 🔒 使用Argon2id进行密钥派生,采用RFC 9106推荐的高内存参数
- 🔒 使用AES-256-GCM进行加密,提供数据完整性验证
- 🔒 支持安全删除明文文件
- 🔒 所有密码操作使用安全的getpass模块

#### 错误处理优化
- ✅ 添加文件格式验证
- ✅ 完善密码错误处理
- ✅ 增加数据完整性检查
- ✅ 优化错误提示信息

### 📁 文件与结构调整

#### 新增文件
- 📄 encrypt_csv.py - 加密模块
- 📄 decrypt_utils.py - 解密模块
- 📄 doc/prd.md - 产品需求文档
- 📄 doc/erd.md - 工程结构设计文档
- 📄 doc/todolist.md - 开发任务清单
- 📄 doc/cursor-log.md - 开发日志

### 💬 备注说明

#### 开发说明
- 📝 所有代码均添加了详细的中文注释
- 📝 函数都有完整的文档字符串
- 📝 遵循Python代码规范

#### 下一步计划
- 📋 编写项目README文档
- 📋 考虑支持YAML/JSON格式
- 📋 考虑添加密码管理器集成

#### 使用注意
- ⚠️ 需要Python 3.6+
- ⚠️ 依赖cryptography和argon2-cffi库
- ⚠️ 密码错误或数据被篡改时会提示错误 