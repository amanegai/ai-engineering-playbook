# 環境構築テンプレート

> 新規プロジェクトの `docs/SETUP.md` に複製してください。

## 前提条件

| ツール | バージョン要件 | インストール |
|------|---------|---------|
| Node.js | 20.x | nvm |
| Docker Desktop | 最新安定版 | docker.com |
| Git | 最新安定版 | git-scm.com |
| Cursor | 最新版 | cursor.com |

## 構築手順

### 1. Node.js をインストール

```bash
nvm install
nvm use
node -v
```

### 2. リポジトリをクローン

```bash
git clone --recurse-submodules https://github.com/<org>/<project>.git
cd <project>
```

### 3. ローカルの PostgreSQL を起動

```bash
docker compose -f docker-compose.dev.yml up -d
```

### 4. 環境変数の設定

```bash
cp .env.example .env.local
```

### 5. 依存関係のインストール

```bash
npm install
```

### 6. DB マイグレーションの実行

```bash
npx prisma migrate dev --schema db/<project>/prisma/schema.prisma
```

### 7. シードデータの投入

```bash
npx prisma db seed
```

### 8. 開発サーバーの起動

```bash
npm run dev
```

http://localhost:3000 を開き、正常に動作することを確認します。

## 日常開発

### 最新コードの取得

```bash
git pull
git submodule update --remote
npm install
npx prisma migrate dev --schema db/<project>/prisma/schema.prisma
```

## よくある質問

（プロジェクト固有の FAQ はここに追記）
