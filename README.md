# AI Engineering Playbook

社内の AI 併用開発のための標準（プレイブック）リポジトリです。プロジェクトの立ち上げから設計・実装・デプロイまでの全工程を規定し、Cursor / AI がそのまま使えるテンプレート、プロンプト、受け入れチェックリストを提供します。

## 用途

- **人が読む**：統一された開発フロー、設計ルール、命名規則
- **AI に使う**：プロンプトのひな形、出力形式の契約、受け入れチェックリスト
- **各プロジェクトで使う**：新規プロジェクト立ち上げ時にテンプレートを複製して標準に沿って進める

## リポジトリ構造

```
ai-engineering-playbook/
├── 00-governance/           # ガバナンス：開発方針、AI 協業ルール
├── 01-project-lifecycle/    # プロジェクトライフサイクル各段階の説明
├── 02-architecture/         # アーキテクチャ規約（フロント/バック/DB/認証）
├── 03-engineering-standards/ # 工学スタンダード（命名/API/Git/Review）
├── 04-ai-workflows/         # AI ワークフロー（プロンプト/出力契約/受け入れ）
├── 05-templates/            # そのまま使えるドキュメントテンプレート
├── 06-reference-projects/   # 参考プロジェクトからの学び（回収）
└── 07-assets/               # 図、例
```

## クイックスタート：新規プロジェクトの立ち上げ

```
1. 05-templates/project-kickoff-template.md を複製して基本情報を記入
2. 05-templates/requirements-template.md を複製して要件を書く（AI 併用可）
3. 04-ai-workflows/prompts/requirements/ を使って要件の初稿を生成
4. 04-ai-workflows/prompts/design/ を使って基本設計/詳細設計/API/DB 草案を生成
5. 04-ai-workflows/acceptance-checklists/ で AI 出力を受け入れ確認
6. 04-ai-workflows/prompts/implementation/ を使って実装タスクを分解し支援
7. プロジェクト完了後 → 06-reference-projects/ に学びを回収
```

## 関連リポジトリ

| リポジトリ | 用途 |
|------|------|
| `company-databases` | 各プロジェクトの DB スキーマを統一管理 |
| `interview-management` | 本スタンダードに従って作った最初のプロジェクト（参考） |
| `employee-info-management` | OA システム（既存。徐々に標準へ寄せる） |

## AI 協業原則（要約）

詳細は [00-governance/ai-collaboration-policy.md](00-governance/ai-collaboration-policy.md) を参照してください。

- AI が下書きを作成し、人が確認して実行する
- 各 AI タスクは固定の入力/出力形式と受け入れ基準を持つ
- DB スキーマ変更、権限モデル、プロダクション設定は必ず人が審査する
- 開発中に学びを本リポジトリへ継続回収する
