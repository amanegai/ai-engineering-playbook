# AI プロンプト：DB 設計生成

## 使用場面

要件ドキュメントとデータモデルの概要から、Prisma schema とテーブル定義書を生成します。

## 入力（使用前に記入）

```
要件ドキュメントのパス：docs/REQUIREMENTS.md
プロジェクト DB ディレクトリ：company-databases/<project-name>/
ORM：Prisma
データベース：PostgreSQL
命名規約：テーブル名は snake_case 複数形、カラム名は snake_case
```

## プロンプト

```
ai-engineering-playbook/05-templates/detailed-design-template.md の「DB」部分を参照し、
以下の要件から Prisma schema とテーブル定義書を生成してください。

【要件ドキュメント】
（docs/REQUIREMENTS.md のデータモデル部分を貼り付け/参照）

【制約】
1. Prisma schema の文法を使う
2. テーブル名は snake_case の複数形、カラム名は snake_case
3. 主キーは UUID（@id @default(uuid())）
4. すべてのテーブルに created_at（@default(now())）を含める
5. ソフトデリートが必要なテーブルには deleted_at を追加する
6. 外部キー関係を明確に定義する
7. 推奨インデックスを明記する

【出力形式】
1. prisma/schema.prisma の完全な内容
2. テーブル定義書（各テーブルの列説明、インデックス、関連）
3. シードデータ提案（どのテーブルに初期データが必要か）
4. マイグレーション順序の説明
```

## 出力受け入れ

`04-ai-workflows/acceptance-checklists/design-checklist.md` で確認してください。

## 次のステップ

1. 人が schema をレビューし、フィールドと関係を確認
2. company-databases リポジトリで schema を作成し、マイグレーションを生成
3. 各開発者がローカルで migrate dev を実行して同期
