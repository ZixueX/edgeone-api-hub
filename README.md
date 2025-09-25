# EdgeOne Pages API Hub

基于腾讯云 EdgeOne Pages 的统一 API 代理服务，提供多平台 API 的高速、稳定访问。特别优化了 Telegram Bot API 在国内的访问体验。

## ✨ 主要特性

🚀 **高性能代理** - 基于 EdgeOne Pages Node Functions，全球 CDN 加速
🌐 **多平台支持** - OpenAI、Gemini、Claude、Grok、Telegram、GitHub 等
🛡️ **安全可靠** - 完整的 CORS 支持，无状态设计，不存储用户数据
📱 **友好界面** - 现代化 Web 界面，一键复制 API 端点
🔧 **智能适配** - 自动域名检测，兼容各种部署环境

## 🎯 解决的问题

- **网络访问限制** - 解决国内访问 OpenAI、Telegram 等服务的网络问题
- **API 统一管理** - 提供统一的代理入口，简化 API 调用
- **全球加速** - 利用 EdgeOne CDN 网络，提供最佳访问速度
- **开发便利** - 无需修改现有代码，直接替换 API 域名即可

## 📊 支持的服务

| 服务 | 描述 | 代理路径 | 特殊优化 |
|------|------|----------|----------|
| **OpenAI** | GPT、DALL-E、Whisper 等 AI 服务 | `/openai/*` | 国内高速访问 |
| **Gemini** | Google 生成式 AI 服务 | `/gemini/*` | 完整 API 支持 |
| **Claude** | Anthropic 对话式 AI 服务 | `/claude/*` | 流式响应支持 |
| **Grok** | xAI 聊天机器人服务 | `/grok/*` | 实时对话 |
| **Telegram** | Telegram Bot API | `/telegram/*` | 🔥 国内直连优化 |
| **GitHub** | 代码仓库和 API 服务 | `/github/*` | 开发者友好 |
| **Docker** | 容器镜像服务 | `/docker/*` | 直连加速 |

## 🚀 快速开始

### 基本使用

访问部署后的域名，查看可用的 API 服务列表。所有 API 调用只需要将原始域名替换为代理域名即可。

### Telegram Bot 示例

```javascript
// 原始调用（可能被限制）
const response = await fetch('https://api.telegram.org/bot<TOKEN>/getMe');

// 使用代理（国内可直接访问）
const response = await fetch('https://your-domain.com/telegram/bot<TOKEN>/getMe');
```

### OpenAI API 示例

```javascript
// 原始调用
fetch('https://api.openai.com/v1/chat/completions', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    model: "gpt-3.5-turbo",
    messages: [{"role": "user", "content": "Hello!"}]
  })
});

// 使用代理
fetch('https://your-domain.com/openai/v1/chat/completions', {
  // 其他参数完全相同，只需替换域名
});
```

## 🏗️ 技术架构

### 核心组件

- **Node Functions** - 使用 EdgeOne Pages 的完整 Node.js 环境
- **智能路由** - 根路径和通配符路由的完美配合
- **域名适配** - 自动检测和过滤内部域名，显示正确的服务地址
- **错误处理** - 完善的异常处理和降级机制

### 文件结构

```
edgeone-api-hub/
├── node-functions/
│   ├── index.js          # 根路径处理器（首页）
│   └── [...path].js      # 通配符路由（API 代理）
├── favicon.ico           # 网站图标
├── package.json          # 项目配置
└── README.md            # 项目文档
```

### 核心特性

🔄 **智能域名检测** - 自动过滤 EdgeOne 内部域名，显示用户的自定义域名
⚡ **异步文件操作** - 支持真实文件读取和优雅降级
🛡️ **兼容性修复** - 完美适配 EdgeOne Pages 的 request/headers API
📝 **详细日志** - 丰富的调试信息，便于问题排查

## 🔧 高级配置

### 环境变量支持

可以通过环境变量自定义配置：

```bash
CUSTOM_DOMAIN=your-custom-domain.com  # 自定义域名
```

### 添加新的 API 服务

修改 `API_CONFIGS` 对象即可添加新的代理服务：

```javascript
const API_CONFIGS = {
  // 现有服务...
  newapi: {
    host: 'api.newservice.com',
    paths: ['/v1/'],
    description: "新服务 API 代理",
    logo: "🆕"
  }
};
```

## 🔍 监控和调试

EdgeOne Pages 提供完整的监控能力：

- **实时日志** - 查看详细的请求处理日志
- **性能监控** - 监控响应时间和成功率
- **错误追踪** - 自动记录和分析错误信息
- **资源使用** - 监控内存和 CPU 使用情况

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 项目
2. 创建功能分支
3. 提交更改
4. 发起 Pull Request

## 📄 开源协议

MIT License - 详见 [LICENSE](LICENSE) 文件

## 👤 作者

**KK**
GitHub: [@ImKK666](https://github.com/ImKK666)

## ⭐ 支持项目

如果这个项目对你有帮助，请给个 Star ⭐！

---


*基于腾讯云 EdgeOne Pages 构建 | 全球加速访问 | 高可用保障*
