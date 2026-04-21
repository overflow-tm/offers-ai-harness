# Offers AI Harness — AGENTS.md

このリポジトリは Offers プラットフォームの MCP サーバーと接続し、求人マッチング・年収チェック・プロフィールレビューを実行する AI エージェント Skill を提供する。

## MCP サーバー接続

`~/.codex/config.toml` に以下を追加:

```toml
[mcp_servers.offers_worker]
url = "https://mcp.offers.jp/worker"
```

認証: OAuth 2.1 + PKCE（初回アクセス時にブラウザが開く）

## 利用可能な MCP ツール

| ツール | 概要 |
|--------|------|
| `get_profile` | ログインユーザーのプロフィール取得 |
| `update_profile` | プロフィール更新 |
| `search_skills` | スキル検索（「バックエンド」等のカテゴリ対応） |
| `search_positions` | 職種検索（「エンジニア」等のカテゴリ対応） |
| `search_jobs` | 求人検索（スキル・職種・勤務地等で絞り込み） |
| `get_job_detail` | 求人詳細取得 |

## Skill 一覧

- `skills/offers-job-match/SKILL.md` — プロフィールベースの求人マッチング
- `skills/offers-career-check/SKILL.md` — スキルセットベースの年収相場チェック
- `skills/offers-profile-review/SKILL.md` — プロフィールレビュー + 改善実行

各 SKILL.md に実行フロー・出力フォーマット・制約が記載されている。
