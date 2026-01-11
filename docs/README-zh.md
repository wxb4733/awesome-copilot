# 🤖 Awesome GitHub Copilot 定制化集合

[![Powered by Awesome Copilot](https://img.shields.io/badge/Powered_by-Awesome_Copilot-blue?logo=githubcopilot)](https://aka.ms/awesome-github-copilot)

一个由社区创建的定制化代理、提示词和指令集合，旨在为不同领域、编程语言和使用场景增强您的 GitHub Copilot 体验。

## 📖 目录

- [什么是 Awesome GitHub Copilot](#什么是-awesome-github-copilot)
- [核心功能](#核心功能)
- [快速开始](#快速开始)
- [MCP 服务器](#mcp-服务器)
- [使用方法](#使用方法)
- [为什么选择 Awesome GitHub Copilot](#为什么选择-awesome-github-copilot)
- [贡献指南](#贡献指南)
- [仓库结构](#仓库结构)
- [资源链接](#资源链接)

## 🚀 什么是 Awesome GitHub Copilot？

Awesome GitHub Copilot 是一个综合性的工具集，通过以下专门的定制化内容来增强 GitHub Copilot：

### 核心组件

| 组件 | 说明 | 文档链接 |
|------|------|----------|
| **🤖 自定义代理 (Custom Agents)** | 集成 MCP 服务器的专门化 GitHub Copilot 代理，为特定工作流程和工具提供增强功能 | [查看详情](README.agents.md) |
| **🎯 提示词 (Prompts)** | 面向任务的专注提示词，用于生成代码、文档和解决特定问题 | [查看详情](README.prompts.md) |
| **📋 指令 (Instructions)** | 适用于特定文件模式或整个项目的全面编码标准和最佳实践 | [查看详情](README.instructions.md) |
| **📦 集合 (Collections)** | 围绕特定主题和工作流程组织的相关提示词、指令和聊天模式的精选集合 | [查看详情](README.collections.md) |

## 🌟 核心功能

### 🤖 自定义代理

自定义代理是专门化的 AI 助手，可以：
- 与 MCP (Model Context Protocol) 服务器集成
- 为特定技术栈提供专业支持
- 自动化复杂的开发工作流程
- 提供上下文感知的代码建议

**应用场景：**
- DevOps 自动化
- 安全审计和漏洞扫描
- 数据库架构设计
- 云基础设施管理
- 特性标志管理
- CI/CD 流程优化

### 🎯 提示词

提示词是预构建的模板，可以：
- 快速执行常见开发任务
- 保持一致的代码生成标准
- 加速项目搭建和配置
- 提供最佳实践指导

**热门提示词包括：**
- 创建 README 文档
- 生成架构决策记录 (ADR)
- 容器化应用程序
- 创建 GitHub Actions 工作流
- 代码审查和重构
- 文档生成

### 📋 指令

指令提供持续的指导：
- 自动应用于匹配文件模式
- 强制执行编码标准
- 确保框架最佳实践
- 保持代码一致性

**覆盖领域：**
- 特定编程语言标准
- 框架约定
- 项目架构模式
- 安全最佳实践
- 测试策略

### 📦 集合

集合将相关资源组合在一起：
- 主题化的开发工作流
- 技术栈特定的工具
- 端到端项目模板
- 学习路径

**精选集合：**
- Awesome Copilot - 元提示词集合
- 合作伙伴工具 - GitHub 合作伙伴创建的自定义代理
- 安全最佳实践
- 云开发工具
- 语言特定开发工具包

## 🚀 快速开始

### MCP 服务器

为了方便在编辑器中添加这些定制化内容，我们创建了一个 [MCP 服务器](https://developer.microsoft.com/blog/announcing-awesome-copilot-mcp-server)，它提供了直接从此仓库搜索和安装提示词、指令和聊天模式的功能。您需要安装并运行 Docker。

[![在 VS Code 中安装](https://img.shields.io/badge/VS_Code-安装-0098FF?logo=visualstudiocode&logoColor=white)](https://aka.ms/awesome-copilot/mcp/vscode) 
[![在 VS Code Insiders 中安装](https://img.shields.io/badge/VS_Code_Insiders-安装-24bfa5?logo=visualstudiocode&logoColor=white)](https://aka.ms/awesome-copilot/mcp/vscode-insiders) 
[![在 Visual Studio 中安装](https://img.shields.io/badge/Visual_Studio-安装-C16FDE?logo=visualstudio&logoColor=white)](https://aka.ms/awesome-copilot/mcp/vs)

<details>
<summary>显示 MCP 服务器 JSON 配置</summary>

```json
{
  "servers": {
    "awesome-copilot": {
      "type": "stdio",
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "ghcr.io/microsoft/mcp-dotnet-samples/awesome-copilot:latest"
      ]
    }
  }
}
```

</details>

## 🔧 使用方法

### 使用自定义代理

自定义代理可以在 Copilot 编码代理 (CCA)、VS Code 和 Copilot CLI 中使用：

- **在 CCA 中**：将问题分配给 Copilot 时，从提供的列表中选择自定义代理
- **在 VS Code 中**：在代理会话中激活自定义代理，与内置的 Plan 和 Agent 并列使用

### 使用提示词

在 GitHub Copilot Chat 中使用 `/` 命令访问提示词：

```plaintext
/awesome-copilot create-readme
```

或者：
1. 点击提示词旁边的 **VS Code** 或 **VS Code Insiders** 安装按钮
2. 在 VS Code Chat 中使用 `/prompt-name` 格式运行
3. 从命令面板运行 `Chat: Run Prompt` 命令
4. 在 VS Code 中打开提示词文件时点击运行按钮

### 使用指令

指令会根据文件模式自动应用：
1. 将 `.instructions.md` 文件添加到 `instructions/` 目录
2. 指令将自动应用于匹配的文件类型
3. 为编码标准、框架和最佳实践提供上下文指导

### 使用集合

集合将相关的提示词、指令和代理组合在一起：
1. 浏览 [集合目录](../collections/)
2. 选择与您的工作流程匹配的集合
3. 按照集合中的指南安装包含的资源

## 💡 为什么选择 Awesome GitHub Copilot？

### 提高生产力
- ⚡ 预构建的代理、提示词和指令节省时间
- 🎯 提供一致且可靠的结果
- 🔄 减少重复性任务

### 最佳实践
- ✅ 受益于社区精选的编码标准和模式
- 📚 从经验丰富的开发者那里学习
- 🛡️ 遵循行业安全标准

### 专业化协助
- 🎓 通过专门化的自定义代理获得专家级指导
- 🔧 访问特定于技术栈的工具
- 🌐 跨多个编程语言和框架的支持

### 持续学习
- 📈 紧跟各种技术的最新模式和实践
- 🔄 定期更新来自社区
- 🎯 根据您的需求定制学习路径

## 🤝 贡献指南

我们欢迎贡献！请查看我们的[贡献指南](../CONTRIBUTING.md)了解如何：

- 添加新的提示词、指令或聊天模式
- 改进现有内容
- 报告问题或提出改进建议

### 快速贡献指南

1. **遵循文件命名约定**：使用小写字母和连字符
2. **添加前置元数据**：包含描述和相关标签
3. **彻底测试您的贡献**：确保在实际场景中运行良好
4. **更新相应的 README 表格**：添加您的贡献到文档中
5. **提交带有清晰描述的 Pull Request**

## 📁 仓库结构

```plaintext
awesome-copilot/
├── prompts/          # 任务特定提示词 (.prompt.md)
├── instructions/     # 编码标准和最佳实践 (.instructions.md)
├── agents/           # AI 角色和专门化模式 (.agent.md)
├── collections/      # 相关项目的精选集合 (.collection.yml)
├── docs/             # 文档文件
├── scripts/          # 维护实用脚本
└── eng/              # 工程工具和脚本
```

## 📚 资源链接

### 官方文档
- [VS Code Copilot 定制化文档](https://code.visualstudio.com/docs/copilot/copilot-customization)
- [GitHub Copilot Chat 文档](https://code.visualstudio.com/docs/copilot/chat/copilot-chat)
- [自定义聊天模式](https://code.visualstudio.com/docs/copilot/chat/chat-modes)
- [VS Code 设置](https://code.visualstudio.com/docs/getstarted/settings)

### 社区资源
- [贡献指南](../CONTRIBUTING.md)
- [行为准则](../CODE_OF_CONDUCT.md)
- [安全政策](../SECURITY.md)
- [支持指南](../SUPPORT.md)

### 快速链接
- 🏠 [主 README](../README.md)
- 🤖 [自定义代理文档](README.agents.md)
- 🎯 [提示词文档](README.prompts.md)
- 📋 [指令文档](README.instructions.md)
- 📦 [集合文档](README.collections.md)

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](../LICENSE) 文件。

## 🛡️ 安全与支持

- **安全问题**：请查看我们的[安全政策](../SECURITY.md)
- **支持**：查看我们的[支持指南](../SUPPORT.md)获取帮助
- **行为准则**：我们遵循[贡献者公约](../CODE_OF_CONDUCT.md)

## ℹ️ 免责声明

此仓库中的定制化内容来源于第三方开发者并由他们创建。GitHub 不验证、认可或保证这些代理的功能或安全性。在安装之前，请仔细检查任何代理及其文档，以了解它可能需要的权限和可能执行的操作。

---

**准备好增强您的编码体验了吗？** 开始探索我们的[提示词](README.prompts.md)、[指令](README.instructions.md)和[自定义代理](README.agents.md)吧！

## 🌟 贡献者

感谢所有为此项目做出贡献的出色人士！查看完整的贡献者列表，请访问主 [README 文件](../README.md#contributors-)。

---

**语言版本：** [English](../README.md) | [简体中文](README-zh.md)
