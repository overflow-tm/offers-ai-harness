# offers-ai-harness

Offers プラットフォームと AI エージェント（Claude Code, Codex CLI, Cursor, gh skills）を接続する Plugin。

## セットアップ

### Claude Code

```bash
/plugin install github.com/overflow-tm/offers-ai-harness
```

### Codex CLI

`$skill-installer` でインストール後、`~/.codex/config.toml` に MCP 接続設定を追加（詳細は AGENTS.md 参照）。

### Cursor

将来対応予定（マーケットプレイス公開時）。

### gh skills

```bash
gh skills add overflow-tm/offers-ai-harness
```

## 提供する Skill

| Skill | 概要 |
|-------|------|
| `/offers-job-match` | プロフィールベースの求人マッチング |
| `/offers-career-check` | スキルセットベースの年収相場チェック |
| `/offers-profile-review` | プロフィールレビュー + 改善実行 |

## 前提条件

- [Offers](https://offers.jp/) アカウント（プロフィール・スキル登録済み）
- 対応ツール: Claude Code / Codex CLI / gh skills
- 初回利用時に OAuth 認証が必要（ブラウザが開きます）

## MCP サーバー

| 環境 | URL |
|------|-----|
| 本番 | `https://mcp.offers.jp/worker` |

## ライセンス

Apache License 2.0
