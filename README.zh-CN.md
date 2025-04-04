# Backblaze B2 的 S3 预签名 URL 生成器

这是一个使用 Go 编写的应用程序，用于为指定的 Backblaze B2 存储桶中的所有对象生成 S3 兼容的预签名 URL。生成的 URL 可用于安全地下载对象，并将生成的链接写入 `presigned_urls.txt` 文件中。

## Language 语言
[English](https://github.com/JasonL111/S3_presigned_URL)

## 功能特色

- **生成预签名 URL**：为存储桶中的所有对象，或带有特定前缀的对象生成预签名下载链接。
- **自定义链接过期时间**：可设置预签名 URL 的过期时间。
- **环境变量配置**：通过 `.env` 文件管理配置和凭证，保证安全性。
- **支持对象前缀筛选**：可选择性地仅生成特定前缀对象的下载链接。

## 前置条件

- **Go 环境**：需安装 Go 语言环境（推荐 Go 1.16 或更高版本）。
- **Backblaze B2 账号**：需要一个 B2 账号以及应用密钥和密钥 ID。

## 安装步骤

1. **克隆仓库**：
```bash
git clone https://github.com/JasonL111/S3_presigned_URL.git
cd S3_presigned_URL
```

2. **安装依赖包**：
```bash
go mod tidy
```
## 使用方法

1. 配置 .env 文件： 在项目根目录下创建一个 .env 文件，示例内容如下：
```bash
B2_KEY_ID=你的密钥ID
B2_APPLICATION_KEY=你的应用密钥
B2_ENDPOINT=你的B2端点（Endpoint）
B2_REGION=你的区域（Region）
B2_BUCKET_NAME=你的存储桶名称
PREFIX=可选的对象前缀（可留空）
```
配置说明：

B2端点(Endpoint)需要包含 https:// 前缀，例如：https://s3.us-west-001.backblazeb2.com
区域(Region)可以从端点提取，示例：
若端点为 s3.us-west-001.backblazeb2.com，则区域为 us-west
Backblaze B2端点和密钥信息可以在您的 Backblaze 账户首页中找到
```bash
go run main.go
```
## 项目依赖
- AWS SDK for Go v2：使用 Apache 2.0 开源许可，详见 NOTICE2.txt
- godotenv：使用 MIT 开源许可，详见 https://mit-license.org/

## 授权许可

本项目采用 Apache 2.0 许可协议，详见项目中的 LICENSE 文件。
本代码基于 aws-doc-sdk-examples 项目构建，遵循 Apache 2.0 许可，相关声明请参阅 NOTICE 文件。
