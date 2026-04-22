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

## ライセンス

[Apache License 2.0](./LICENSE)
