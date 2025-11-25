# Claude Context Enhanced

### An enhanced fork of claude-context with stability fixes and improved reliability

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-20%2B-green.svg)](https://nodejs.org/)
[![Based on](https://img.shields.io/badge/Based%20on-claude--context-orange.svg)](https://github.com/zilliztech/claude-context)

---

## Overview

**Claude Context Enhanced** is a stability-focused fork of [claude-context](https://github.com/zilliztech/claude-context) with critical bug fixes and performance improvements. This enhanced version ensures reliable snapshot persistence, faster synchronization, and improved data availability for your semantic code search needs.

### Key Enhancements

This fork includes the following improvements over the original claude-context:

- **Fixed Snapshot Persistence** - Resolved critical issue where snapshots weren't being saved after indexing
- **Improved Background Sync** - Reduced sync interval from 5 minutes to 2 minutes for faster updates
- **Automatic Milvus Flush** - Added automatic flush after indexing to ensure immediate data availability
- **Enhanced Health Checks** - Comprehensive MCP server configuration validation and health monitoring
- **Better File Management** - Added comprehensive context ignore patterns for cleaner indexing

---

## What is Claude Context?

**Claude Context** is an MCP plugin that adds semantic code search to Claude Code and other AI coding agents, giving them deep context from your entire codebase.

🧠 **Your Entire Codebase as Context**: Uses semantic search to find all relevant code from millions of lines, bringing results straight into Claude's context.

💰 **Cost-Effective for Large Codebases**: Efficiently stores your codebase in a vector database and only uses related code in context to keep costs manageable.

---

## Quick Start

### Prerequisites

<details>
<summary>Get a free vector database on Zilliz Cloud</summary>

Claude Context needs a vector database. You can [sign up](https://cloud.zilliz.com/signup?utm_source=github&utm_medium=referral&utm_campaign=2507-codecontext-readme) on Zilliz Cloud to get an API key.

Copy your Personal Key to replace `your-zilliz-cloud-api-key` in the configuration examples.
</details>

<details>
<summary>Get OpenAI API Key for embedding model</summary>

You need an OpenAI API key for the embedding model. Get one at [OpenAI](https://platform.openai.com/api-keys).

Your API key starts with `sk-`. Copy your key and use it in the configuration examples below as `your-openai-api-key`.
</details>

### Configure MCP for Claude Code

**System Requirements:**

- Node.js >= 20.0.0 and < 24.0.0

> Claude Context is not compatible with Node.js 24.0.0, you need to downgrade it first if your node version is greater or equal to 24.

#### Configuration

Use the command line interface to add the Claude Context Enhanced MCP server:

```bash
# Install from npm (coming soon)
claude mcp add claude-context-enhanced \
  -e OPENAI_API_KEY=sk-your-openai-api-key \
  -e MILVUS_TOKEN=your-zilliz-cloud-api-key \
  -- npx claude-context-enhanced@latest

# Or install from GitHub
claude mcp add claude-context-enhanced \
  -e OPENAI_API_KEY=sk-your-openai-api-key \
  -e MILVUS_TOKEN=your-zilliz-cloud-api-key \
  -- npx @gitabozaid/claude-context-enhanced@latest
```

See the [Claude Code MCP documentation](https://docs.anthropic.com/en/docs/claude-code/mcp) for more details about MCP server management.

---

### Usage in Your Codebase

1. **Open Claude Code**

   ```bash
   cd your-project-directory
   claude
   ```

2. **Index your codebase**:

   ```
   Index this codebase
   ```

3. **Check indexing status**:

   ```
   Check the indexing status
   ```

4. **Start searching**:

   ```
   Find functions that handle user authentication
   ```

🎉 **That's it!** You now have enhanced semantic code search with improved reliability.

---

## Features

All features from the original claude-context, plus:

- 🔍 **Hybrid Code Search**: BM25 + dense vector search
- 🧠 **Context-Aware**: Understand code relationships across millions of lines
- ⚡ **Incremental Indexing**: Efficiently re-index only changed files using Merkle trees
- 🧩 **Intelligent Code Chunking**: AST-based code analysis
- 🗄️ **Scalable**: Integrates with Zilliz Cloud for scalable vector search
- 🛠️ **Customizable**: Configure file extensions, ignore patterns, and embedding models
- **Enhanced Stability**: Critical fixes for snapshot persistence and data availability
- **Faster Sync**: Reduced background sync interval for quicker updates

---

## Available Tools

#### 1. `index_codebase`

Index a codebase directory for hybrid search (BM25 + dense vector).

#### 2. `search_code`

Search the indexed codebase using natural language queries with hybrid search.

#### 3. `clear_index`

Clear the search index for a specific codebase.

#### 4. `get_indexing_status`

Get the current indexing status of a codebase with progress percentage.

---

## Development

### Setup Development Environment

```bash
# Clone repository
git clone https://github.com/gitabozaid/claude-context-enhanced.git
cd claude-context-enhanced

# Install dependencies
pnpm install

# Build all packages
pnpm build

# Start development mode
pnpm dev
```

### Building

```bash
# Build all packages
pnpm build

# Build specific package
pnpm build:core
pnpm build:vscode
pnpm build:mcp
```

---

## Changelog

### Enhancements in this fork:

- **v0.1.3-enhanced**
  - Fixed snapshot not saving after successful indexing
  - Reduced background sync interval from 5 minutes to 2 minutes
  - Added automatic Milvus flush after indexing for immediate data availability
  - Resolved MCP server configuration issues with comprehensive health checks
  - Added comprehensive context ignore patterns

---

## Contributing

Contributions are welcome! This project maintains compatibility with the original [claude-context](https://github.com/zilliztech/claude-context) while adding stability improvements.

---

## Acknowledgments

This project is a fork of [claude-context](https://github.com/zilliztech/claude-context) by Zilliz. Special thanks to the original maintainers for creating such a powerful tool.

**Original Project**: [zilliztech/claude-context](https://github.com/zilliztech/claude-context)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Same license as the original project.

---

## Links

- **This Fork**: [github.com/gitabozaid/claude-context-enhanced](https://github.com/gitabozaid/claude-context-enhanced)
- **Original Project**: [github.com/zilliztech/claude-context](https://github.com/zilliztech/claude-context)
- [Milvus Documentation](https://milvus.io/docs)
- [Zilliz Cloud](https://zilliz.com/cloud)
