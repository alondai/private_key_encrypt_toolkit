# 开发任务清单（ToDoList）

## encrypt_csv.py
- [x] 接收 `add.csv` 作为输入  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 安全输入用户密码（使用 getpass）  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 生成 salt 和 nonce  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 使用 Argon2id 派生 AES 密钥  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 使用 AES-256-GCM 加密数据  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 输出加密结果为 encrypted_add.csv  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 可选删除 add.csv 明文  # 完成人: Cursor, 完成时间: 2024-03-27

## decrypt_utils.py
- [x] 实现 decrypt_csv(file_path, password)  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 读取 salt 和 nonce  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 派生密钥并使用 AES-256-GCM 解密  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 转换为 DataFrame 返回  # 完成人: Cursor, 完成时间: 2024-03-27
- [x] 提供异常处理机制（如密码错误）  # 完成人: Cursor, 完成时间: 2024-03-27

## 文档与辅助
- [x] 编写使用说明（README）  # 完成人: Cursor, 完成时间: 2024-03-27