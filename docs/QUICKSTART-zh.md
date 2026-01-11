# 🚀 快速开始指南

欢迎使用 Awesome GitHub Copilot！本指南将帮助您快速上手，在几分钟内开始使用定制化的代理、提示词和指令。

## 📋 目录

- [前提条件](#前提条件)
- [安装 MCP 服务器](#安装-mcp-服务器)
- [第一个提示词](#第一个提示词)
- [使用指令](#使用指令)
- [使用自定义代理](#使用自定义代理)
- [探索集合](#探索集合)
- [常见问题](#常见问题)
- [下一步](#下一步)

## ✅ 前提条件

在开始之前，请确保您已经：

1. **安装 GitHub Copilot**
   - 拥有有效的 GitHub Copilot 订阅
   - 在 VS Code 或 Visual Studio 中安装了 GitHub Copilot 扩展

2. **安装 Docker**（使用 MCP 服务器时需要）
   - [下载 Docker Desktop](https://www.docker.com/products/docker-desktop)
   - 确保 Docker 正在运行

3. **编辑器版本**
   - VS Code 1.85 或更高版本
   - 或 Visual Studio 2022 17.8 或更高版本

## 🔧 安装 MCP 服务器

MCP (Model Context Protocol) 服务器让您可以轻松浏览和安装仓库中的定制化内容。

### 方法 1：一键安装（推荐）

点击适合您编辑器的安装按钮：

- [![在 VS Code 中安装](https://img.shields.io/badge/VS_Code-安装-0098FF?logo=visualstudiocode&logoColor=white)](https://aka.ms/awesome-copilot/mcp/vscode)
- [![在 VS Code Insiders 中安装](https://img.shields.io/badge/VS_Code_Insiders-安装-24bfa5?logo=visualstudiocode&logoColor=white)](https://aka.ms/awesome-copilot/mcp/vscode-insiders)
- [![在 Visual Studio 中安装](https://img.shields.io/badge/Visual_Studio-安装-C16FDE?logo=visualstudio&logoColor=white)](https://aka.ms/awesome-copilot/mcp/vs)

### 方法 2：手动配置

如果您更喜欢手动配置：

1. 打开 VS Code 设置 (⌘+, 或 Ctrl+,)
2. 搜索 "MCP Servers"
3. 添加以下配置：

```json
{
  "mcpServers": {
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

4. 重启 VS Code

### 验证安装

1. 打开 GitHub Copilot Chat (⌘+I 或 Ctrl+I)
2. 输入 `@awesome-copilot` 
3. 如果看到服务器响应，说明安装成功！

## 🎯 第一个提示词

让我们尝试一个简单的提示词来为您的项目创建 README 文档。

### 步骤 1：安装提示词

**选项 A：使用 MCP 服务器**
```
在 Copilot Chat 中输入：
@awesome-copilot 搜索 create-readme
```

**选项 B：手动安装**
1. 访问 [prompts 文件夹](../prompts/)
2. 找到 `create-readme.prompt.md`
3. 点击"Install in VS Code"按钮

### 步骤 2：运行提示词

在 Copilot Chat 中输入：
```
/create-readme
```

或者：
1. 打开命令面板 (⌘+Shift+P 或 Ctrl+Shift+P)
2. 输入 "Chat: Run Prompt"
3. 选择 "create-readme"

### 步骤 3：查看结果

Copilot 将：
1. 分析您的项目结构
2. 检查代码和依赖
3. 生成一个全面的 README.md 文件

💡 **提示**：您可以通过聊天进一步完善生成的内容！

## 📋 使用指令

指令会自动应用到您的代码中，无需手动调用。

### 示例：Python 最佳实践指令

1. **下载指令文件**
   ```bash
   # 克隆仓库或下载特定指令文件
   curl -o .github/copilot-instructions.md \
     https://raw.githubusercontent.com/github/awesome-copilot/main/instructions/python-best-practices.instructions.md
   ```

2. **编写 Python 代码**
   - 打开或创建一个 `.py` 文件
   - 开始编写代码
   - Copilot 会自动应用 Python 最佳实践指令

3. **观察效果**
   - 代码建议将遵循 PEP 8 标准
   - 自动包含类型提示
   - 添加适当的文档字符串

### 热门指令推荐

| 指令 | 适用场景 |
|------|----------|
| `python-best-practices` | Python 项目 |
| `react-component-patterns` | React 应用 |
| `security-best-practices` | 所有项目（安全编码） |
| `api-design-patterns` | API 开发 |
| `testing-best-practices` | 测试驱动开发 |

## 🤖 使用自定义代理

自定义代理是专门化的 AI 助手，具有特定领域的专业知识。

### 在 VS Code 中使用代理

1. **打开 Copilot Chat**
   - 按 ⌘+I (Mac) 或 Ctrl+I (Windows/Linux)

2. **激活代理**
   ```
   @agent-name 您的问题或任务
   ```

3. **示例任务**
   ```
   @docker-expert 帮我为这个 Node.js 应用创建一个优化的 Dockerfile
   
   @security-auditor 检查这段代码的安全漏洞
   
   @database-architect 为电商应用设计数据库架构
   ```

### 在 Copilot 编码代理 (CCA) 中使用

当您将 GitHub Issue 分配给 Copilot 时：

1. 在 Issue 页面点击"Assign to Copilot"
2. 从下拉列表中选择自定义代理
3. Copilot 将使用该代理的专业知识来处理任务

### 推荐的首次尝试代理

- **code-reviewer** - 进行全面的代码审查
- **doc-writer** - 生成项目文档
- **test-generator** - 创建单元测试
- **refactoring-assistant** - 改进代码结构

## 📦 探索集合

集合是围绕特定主题组织的资源包。

### 推荐的入门集合

#### 1. Awesome Copilot 集合
元提示词，帮助您发现和生成更多定制化内容。

**如何使用：**
```
在 Copilot Chat 中：
@awesome-copilot 我想创建一个新的自定义提示词
```

#### 2. 安全最佳实践集合
包含安全审计、漏洞扫描和安全编码指令的完整集合。

**包含内容：**
- 代码安全分析提示词
- OWASP Top 10 指令
- 安全审查代理

#### 3. 项目规划集合
帮助您规划和管理开发项目的工具。

**包含内容：**
- 创建技术规范
- 生成项目计划
- 创建架构决策记录 (ADR)

### 浏览所有集合

访问 [collections](../collections/) 目录查看所有可用集合。

## ❓ 常见问题

### Docker 相关

**Q：MCP 服务器必须使用 Docker 吗？**
A：是的，当前 MCP 服务器需要 Docker。作为替代方案，您可以手动下载并安装提示词和指令文件。

**Q：Docker 容器会占用很多资源吗？**
A：不会，容器非常轻量级，仅在需要时运行。

### 提示词相关

**Q：我可以修改现有提示词吗？**
A：可以！下载提示词文件后，您可以根据需要进行自定义。

**Q：如何创建自己的提示词？**
A：查看我们的[贡献指南](../CONTRIBUTING.md)获取详细说明和模板。

### 指令相关

**Q：指令如何应用？**
A：指令根据文件模式（在前置元数据中定义）自动应用到匹配的文件。

**Q：我可以禁用特定指令吗？**
A：可以，从您的 `.github/copilot-instructions.md` 文件中删除或注释掉相应指令即可。

### 代理相关

**Q：代理和提示词有什么区别？**
A：代理是持久的专门化助手，而提示词是一次性使用的模板。代理维护上下文并可以执行复杂的多步骤任务。

**Q：我可以同时使用多个代理吗？**
A：在一个对话中，您一次只能使用一个活跃的代理，但可以在不同任务中切换代理。

## 🎯 下一步

现在您已经了解了基础知识，以下是一些建议的后续步骤：

### 1. 探索更多资源

- 📚 阅读详细的[提示词文档](README.prompts.md)
- 🤖 浏览[自定义代理目录](README.agents.md)
- 📋 查看[指令列表](README.instructions.md)
- 📦 探索[集合目录](README.collections.md)

### 2. 尝试常见工作流程

- 为新项目创建完整的项目结构
- 使用提示词生成测试套件
- 通过代理进行代码审查
- 使用集合设置新的技术栈

### 3. 参与社区

- ⭐ 给仓库加星标
- 🐛 报告问题或建议改进
- 🤝 贡献您自己的提示词、指令或代理
- 💬 在讨论区分享您的经验

### 4. 自定义您的体验

- 根据您的工作流程修改现有提示词
- 为您的团队创建自定义指令
- 构建针对您项目的专门化代理
- 将多个资源组合成自定义集合

## 📚 其他资源

- [完整文档](README-zh.md)
- [贡献指南](../CONTRIBUTING.md)
- [官方 GitHub Copilot 文档](https://docs.github.com/copilot)
- [VS Code Copilot 定制化](https://code.visualstudio.com/docs/copilot/copilot-customization)

---

**需要帮助？** 
- 📖 查看[支持指南](../SUPPORT.md)
- 💬 在 [GitHub Discussions](https://github.com/github/awesome-copilot/discussions) 提问
- 🐛 在 [Issues](https://github.com/github/awesome-copilot/issues) 报告问题

**准备好了吗？开始您的 Awesome Copilot 之旅吧！** 🚀
