# 開発総則

## プロジェクト組織

- 各業務システムは独立した Git リポジトリとする
- DB スキーマの統一は `company-databases` リポジトリで、プロジェクトごとにディレクトリ分割して管理する
- 開発標準、AI ワークフローは本リポジトリ（`ai-engineering-playbook`）で管理する

## 技術スタックの標準

| レイヤ | 第一候補 | 代替（既存プロジェクト） |
|----|------|----------------|
| フルスタック Web | Next.js + TypeScript | — |
| フロント SPA | React + Vite + TypeScript | Bootstrap |
| バックエンド API | Next.js API Routes | Spring Boot（Java） |
| DB | PostgreSQL | — |
| ORM | Prisma | Flyway（Java プロジェクト） |
| スタイル | Tailwind CSS | Bootstrap |
| デプロイ | AWS EC2 上の Docker Compose | — |
| AI 支援 | Cursor | — |

## 設計ドキュメント体系

日本の IT で一般的な設計フェーズに従う：

```
機能設計（要件定義）
  ↓
基本設計（アーキテクチャ、DB、API 概要）
  ↓
詳細設計（画面、API 詳細、DB 表定義）
  ↓
実装 → テスト → デプロイ
```

各フェーズには対応するテンプレート（`05-templates/`）と AI プロンプト（`04-ai-workflows/prompts/`）がある。

## 命名規約（要約）

| 区分 | ルール | 例 |
|------|------|------|
| Git リポジトリ | kebab-case | `interview-management` |
| DB リポジトリ配下 | kebab-case | `company-databases/interview/` |
| API パス | kebab-case 複数形 | `/api/v1/interviews` |
| DB テーブル名 | snake_case 複数形 | `interview_questions` |
| DB カラム名 | snake_case | `created_at` |
| React コンポーネント | PascalCase | `InterviewCard.tsx` |
| 関数/変数 | camelCase | `createInterview()` |
| 型 | PascalCase | `type Interview` |
| 定数 | UPPER_SNAKE_CASE | `MAX_QUESTIONS` |

詳細は `03-engineering-standards/naming-convention.md`（未作成）を参照。

## Git ワークフロー

- `main` は常に安定（安定版）
- 機能開発は `feature/<phase>-<description>` ブランチ
- commit message 形式：`[Phase X] 簡潔説明`
- マージ前に code review
- DB スキーマ変更は指定開発者が統一管理

## 多人数協業

- 各開発者はローカルで Docker により PostgreSQL を起動し、DB 構造は `company-databases` で同期する
- API は先に定義し、プロジェクトの `docs/API.md` に記録する
- 共通 UI コンポーネントは `src/components/ui/` で統一管理
- 毎日短く進捗共有
