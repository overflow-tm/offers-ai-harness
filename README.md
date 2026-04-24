# Offers — AI エージェントで転職活動をもっとスマートに

[Offers](https://offers.jp/) は、AI時代のハイクラスエンジニア・PdM 向け転職プラットフォームです。

このリポジトリは、あなたが普段使っている AI コーディングエージェント（Claude Code, Codex CLI など）から Offers の機能を直接利用するための Skill セットを提供します。

## あなたのスキルに合う求人を、AI が探します

| Skill | できること |
|-------|----------|
| `/offers-job-match` | あなたのプロフィール（スキル・職種・経験年数）をもとに、マッチする求人を検索し、合う点・足りない点を分析します |
| `/offers-career-check` | 同じスキルセットの求人市場での年収相場（下位帯・中央値・上位帯）を算出し、年収アップにつながるスキルを提案します |
| `/offers-profile-review` | プロフィールの強み・弱みをレビューし、改善提案を提示。承認すれば Offers プロフィールをその場で更新できます |

## はじめかた

### 1. Offers アカウントを準備

[offers.jp](https://offers.jp/) でアカウントを作成し、スキル・職種・職歴を登録してください。登録内容が充実しているほど、マッチング精度が上がります。

### 2. AI エージェントにインストール

**Claude Code:**

```bash
# マーケットプレイスを追加（初回のみ）
/plugin marketplace add overflow-tm/offers-ai-harness

# プラグインをインストール
/plugin install offers-ai-harness@offers-ai-harness

# インストール後、MCP 接続が自動設定されます。
# 接続状態は /mcp コマンドで確認できます。
```

<details>
<summary>その他のツール</summary>

**Codex CLI:**

`$skill-installer` でインストール後、`~/.codex/config.toml` に MCP 接続設定を追加してください。詳細は [AGENTS.md](./AGENTS.md) を参照。

**gh skills:**

```bash
gh skills add overflow-tm/offers-ai-harness
```

</details>

### 3. Skill を実行

インストール後、AI エージェントで以下のように話しかけるだけで使えます。

- 「自分に合う求人を探して」→ `/offers-job-match`
- 「年収相場を教えて」→ `/offers-career-check`
- 「プロフィールを見直したい」→ `/offers-profile-review`

初回のみ、ブラウザが開いて Offers アカウントの認証が求められます。

## Offers について

> ハイクラスエンジニア・PdM 向け転職プラットフォーム「Offers」。登録 35,000 人・導入 1,000 社以上の実績。技術背景と志向性を AI が深く分析し、あなたのキャリアを支援します。

- [Offers トップ](https://offers.jp/)
- [求人を探す（Offers Jobs）](https://offers.jp/jobs)
- [利用規約](https://offers.jp/terms)
- [プライバシーポリシー](https://offers.jp/privacypolicy)

## データの取り扱いについて

このプラグインを使用すると、AI エージェントが Offers MCP サーバー（`https://mcp.offers.jp/worker`）と通信し、以下のデータを処理します。ご利用前に必ずご確認ください。

### アクセス・送信されるデータ

| スキル | アクセスするデータ | プロフィール更新 |
|--------|-----------------|--------------|
| `/offers-profile-review` | プロフィール全項目（スキル・職歴・年収・学歴・居住地・アピールポイント・氏名・メールアドレス等） | あり（ユーザー承認時のみ） |
| `/offers-job-match` | プロフィール（スキル・職種・年収・希望条件）、求人情報 | なし |
| `/offers-career-check` | プロフィール（スキル・年収）、求人情報 | なし |

### 通信・認証

- 通信先: `https://mcp.offers.jp/worker`（overflow inc. 運営）
- 認証方式: OAuth 2.1 + PKCE（初回アクセス時にブラウザで認証）
- 通信は HTTPS で暗号化されます

### プロフィールの更新について

`/offers-profile-review` のみがプロフィール更新機能を持ちます。更新は**あなたが明示的に承認した場合のみ**実行され、承認前に変更が行われることはありません。更新可能な項目は以下です。

- 職種、転職意欲、副業意欲
- 現在の年収、希望年収
- 勤務形態、居住地、最終学歴、志向性
- アピールポイント、今後やりたいこと
- スキル（追加・削除）、職歴（追加・更新・削除）、サブ職種（追加・削除）

※ 氏名・メールアドレスは本プラグインでは変更できず、[Offers Web](https://offers.jp/) で直接編集してください。

### AI エージェント側のデータ保持

本プラグインが処理するデータ（年収・職歴・スキル等）は、AI エージェント（Claude Code、Codex CLI 等）の会話コンテキストに含まれます。AI エージェントがデータをどのように保持・利用するかは、各サービスのデータポリシーに従います。ご利用プランにより適用ポリシーが異なる場合があります。

- [Anthropic（Claude Code）プライバシーポリシー](https://www.anthropic.com/privacy)
- [Offers プライバシーポリシー](https://offers.jp/privacypolicy)

### データ取扱いに関するお問い合わせ

データの開示・訂正・削除要求については [Offers プライバシーポリシー](https://offers.jp/privacypolicy) に記載の窓口にご連絡ください。

## ライセンス

[Apache License 2.0](./LICENSE)
