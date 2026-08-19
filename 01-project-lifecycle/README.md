# プロジェクトライフサイクル

開発各フェーズにおける標準フローと、対応するドキュメント/テンプレートを示します。

## フェーズ一覧

| フェーズ | 名称 | 成果物（文書） | テンプレート | AI プロンプト |
|------|------|---------|------|----------|
| 0 | プロジェクト立ち上げ | KICKOFF.md | `05-templates/project-kickoff-template.md` | — |
| 1 | 機能設計（要件） | REQUIREMENTS.md | `05-templates/requirements-template.md` | `04-ai-workflows/prompts/requirements/` |
| 2 | 基本設計 | BASIC-DESIGN.md | `05-templates/basic-design-template.md` | — |
| 3 | 詳細設計 | DETAILED-DESIGN.md | `05-templates/detailed-design-template.md` | `04-ai-workflows/prompts/design/` |
| 4 | 環境構築 | SETUP.md | `05-templates/setup-template.md` | — |
| 5 | 実装 | コード | — | `04-ai-workflows/prompts/implementation/` |
| 6 | テスト | テストレポート | — | — |
| 7 | デプロイ | デプロイドキュメント | — | — |
| 8 | 学びの回収 | lessons-learned.md | — | — |

## フロー図

```
プロジェクト立ち上げ (KICKOFF)
  ↓
要件定義 (REQUIREMENTS) ← AI 支援生成 + 人の確認
  ↓
基本設計 (BASIC-DESIGN) ← AI 支援生成 + 人の確認
  ↓
詳細設計 (DETAILED-DESIGN) ← AI 支援で API/DB/画面 + 人の確認
  ↓
環境構築 (SETUP) → 各開発者のローカル環境が用意できる
  ↓
タスク分解 ← AI 支援
  ↓
各 Phase の実装 ← AI 支援コーディング + 人の review
  ↓
テスト
  ↓
デプロイ
  ↓
学びの回収 → 06-reference-projects/
```

## 各フェーズの詳細

- [01-requirements/](01-requirements/) — 要件定義フェーズ
- [02-basic-design/](02-basic-design/) — 基本設計フェーズ
- [03-detailed-design/](03-detailed-design/) — 詳細設計フェーズ
- [04-implementation/](04-implementation/) — 実装フェーズ
- [05-testing/](05-testing/) — テストフェーズ
- [06-deployment/](06-deployment/) — デプロイフェーズ
