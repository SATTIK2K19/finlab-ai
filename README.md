[English](README.md) | [繁體中文](README.zh-TW.md)

# FinLab AI

> Your AI's shortcut to mass-produce alpha-generating quant strategies.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai)
[![Cursor](https://img.shields.io/badge/Cursor-MCP%20Server-blue)](https://cursor.com)
[![Antigravity](https://img.shields.io/badge/Antigravity-MCP%20Server-green)](https://antigravity.google)

<img src="assets/demo.gif" alt="Demo" width="700">

## Quick Install

### For Cursor Users (One-Click!)

Copy this link to your browser to install:

```
cursor://anysphere.cursor-deeplink/mcp/install?name=finlab&config=eyJ1cmwiOiJodHRwczovL2ZpbmxhYi1haS1wbHVnaW4ua29yZWFsNjgwMy53b3JrZXJzLmRldi9tY3AifQ==
```

### For Antigravity Users

Add this to your MCP config:

```json
{
  "mcpServers": {
    "finlab": {
      "serverUrl": "https://finlab-ai-plugin.koreal6803.workers.dev/mcp"
    }
  }
}
```

No installation needed - the MCP server is hosted remotely!

### For Claude Code / Other AI CLI Users

Simply tell your AI assistant:

> "Please look at https://github.com/koreal6803/finlab-ai and install the FinLab plugin for me"

This works with **Claude Code**, **ChatGPT Codex CLI**, **Gemini CLI**, and other AI coding assistants. AI should follow the [Manual Installation](#manual-installation) instructions below.

## Features

- **Comprehensive Data Access** - 900+ data columns: prices, financials, revenue, valuations, institutional trading
- **Strategy Development** - Factor-based strategies using FinLabDataFrame methods
- **Backtesting Engine** - Risk management, stop-loss, take-profit, position sizing
- **Factor Analysis** - IC calculation, Shapley values, centrality analysis
- **Machine Learning** - Feature engineering and label generation for ML models

## Examples

### Fetch Institutional Trading Data

**Prompt:**
> "List following TW stocks 近 5 天外資買賣超: 2330, 2317, 2454, 2881, 2308, 2382, 2882, 2412, 2303, 2344"

**Result:**

<img src="assets/demo-data.png" alt="Data Output" width="700">

### Build & Backtest a Strategy

**Prompt:**
> "Build a monthly rebalancing strategy for Taiwan stocks: select stocks with positive revenue YoY growth, P/E ratio below 10, P/B ratio below 1.5 (deep value), and price above 60-day moving average (uptrend). Pick top 20 stocks monthly and backtest."

**Result:**

<img src="assets/demo-chart.png" alt="Backtest Result" width="700">

## Manual Installation

> **For AI Assistants:** When a user asks you to install FinLab, follow the instructions below for your platform.

### Claude Code (Skill)

```bash
# Remove if exists (skip if not installed)
claude plugin uninstall finlab-plugin@finlab-plugins
claude plugin marketplace remove finlab-plugins

# Install
claude plugin marketplace add koreal6803/finlab-ai
claude plugin install finlab-plugin@finlab-plugins
```

> AI: Use plugin, not MCP.

### Codex CLI (Skill)

Clone repo, copy `finlab-plugin/skills/finlab` to `~/.codex/skills/`, then delete the cloned repo.

### Gemini CLI (Skill)

```bash
npm install -g skill-porter
```

Clone repo, then run:
```bash
skill-porter convert ./finlab-plugin/skills/finlab --to gemini --output ./finlab-gemini-extension
```

Install the generated `finlab-gemini-extension` following Gemini CLI docs.

### Cursor IDE (MCP)

Add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "finlab": {
      "url": "https://finlab-ai-plugin.koreal6803.workers.dev/mcp"
    }
  }
}
```

### Antigravity IDE (MCP)

Add to MCP config (`mcp_config.json`):

```json
{
  "mcpServers": {
    "finlab": {
      "serverUrl": "https://finlab-ai-plugin.koreal6803.workers.dev/mcp"
    }
  }
}
```

## Documentation

Comprehensive reference docs included:

| Document | Content |
|----------|---------|
| Data Reference | 900+ columns across 80+ tables |
| Backtesting Reference | sim() API, resampling, metrics |
| Factor Examples | 60+ complete strategy examples |
| Best Practices | Patterns, anti-patterns, tips |
| ML Reference | Feature engineering, labels |

## License

MIT

## Author

FinLab Community
