# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 命令

- 构建/部署: `wrangler deploy`
- 开发/启动: `wrangler dev` 或 `wrangler start`
- 运行测试: `vitest`

## 高层架构和结构

该项目是一个Gemini 2.5多模态对话的网站，支持Deno和Cloudflare Worker部署。它将Gemini Chat API的格式转换为更通用的OpenAI格式，方便国内用户直连使用，并可对接AI编程和ChatBox等AI客户端。

### 部署方式
- **Deno部署**: 推荐方式，通过Deno Deploy服务进行无服务器部署。
- **Cloudflare Worker部署**: 通过Cloudflare Worker进行部署，可能需要绑定自定义域名。

### 文件结构
- `deno.json`: Deno配置文件。
- `package.json`: Node.js项目配置文件，包含开发依赖和脚本。
- `README.MD`/`README_EN.MD`: 项目中文/英文介绍和部署说明。
- `src/`: 核心代码目录，包含Deno和Cloudflare Worker的入口文件。
- `test/`: 测试文件目录。
- `vitest.config.js`: Vitest测试框架的配置文件。
- `wrangler.toml`: Cloudflare Worker的配置文件。

### API代理
项目将Gemini API代理为OpenAI格式，允许用户使用OpenAI格式的API请求Gemini服务。 