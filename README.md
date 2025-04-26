# NX Remote Cache Ali OSS

基于阿里云 OSS 的 NX 远程缓存实现，帮助加速团队的构建过程。

[![NPM版本](https://img.shields.io/npm/v/@likesandy/nx-remotecache-ali-oss.svg)](https://www.npmjs.com/package/@likesandy/nx-remotecache-ali-oss)
[![License](https://img.shields.io/npm/l/@likesandy/nx-remotecache-ali-oss.svg)](https://github.com/likesandy/nx-remotecache-ali-oss/blob/main/LICENSE)

## 特性

- 使用阿里云 OSS 作为 NX 远程缓存存储
- 简单配置，易于集成
- 提高团队构建速度

## 安装

```bash
# npm
npm install @likesandy/nx-remotecache-ali-oss --save-dev

# yarn
yarn add @likesandy/nx-remotecache-ali-oss -D

# pnpm
pnpm add @likesandy/nx-remotecache-ali-oss -D
```

## 配置

在您的`nx.json`文件中添加以下配置：

```json
{
  "tasksRunnerOptions": {
    "default": {
      "runner": "nx-remotecache-custom",
      "options": {
        "cacheableOperations": ["build", "test", "lint", "e2e"],
        "customRunner": "@likesandy/nx-remotecache-ali-oss",
        "accessKeyId": "YOUR_ALI_ACCESS_KEY_ID",
        "accessKeySecret": "YOUR_ALI_ACCESS_KEY_SECRET",
        "bucket": "YOUR_OSS_BUCKET_NAME",
        "region": "YOUR_OSS_REGION",
        "folder": "nx-cache"
      }
    }
  }
}
```

您可以通过环境变量来设置敏感信息：

```bash
export ALI_OSS_ACCESS_KEY_ID=your_access_key_id
export ALI_OSS_ACCESS_KEY_SECRET=your_access_key_secret
export ALI_OSS_BUCKET=your_bucket_name
export ALI_OSS_REGION=oss-cn-hangzhou
```

## 配置选项

| 选项            | 环境变量                  | 描述                       | 默认值          |
| --------------- | ------------------------- | -------------------------- | --------------- |
| accessKeyId     | ALI_OSS_ACCESS_KEY_ID     | 阿里云 OSS 访问密钥 ID     | -               |
| accessKeySecret | ALI_OSS_ACCESS_KEY_SECRET | 阿里云 OSS 访问密钥 Secret | -               |
| bucket          | ALI_OSS_BUCKET            | OSS 存储桶名称             | -               |
| region          | ALI_OSS_REGION            | OSS 区域                   | oss-cn-hangzhou |
| folder          | ALI_OSS_FOLDER            | 存储桶中的文件夹路径       | nx-cache        |

## 许可证

MIT
