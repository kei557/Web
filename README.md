# E-commerce Platform

Java Spring Boot + React + MySQLで構築した、商品販売プラットフォームです。

## 機能

- 🛍️ **商品管理**: 商品の作成、編集、削除
- 📦 **在庫管理**: リアルタイム在庫追跡、在庫警告
- 💰 **価格設定**: 基本価格、割引、キャンペーン価格設定
- 👤 **ユーザー認証**: 会員登録、ログイン機能
- 🛒 **ショッピングカート**: 商品選択、数量調整
- 📋 **注文管理**: 注文作成、履歴管理
- 💳 **決済**: 注文処理

## 技術スタック

### バックエンド
- **Java 11+**
- **Spring Boot 2.x**
- **Spring Data JPA**
- **MySQL 8.0**

### フロントエンド
- **React 18+**
- **Axios** (API通信)
- **React Router** (ルーティング)
- **CSS/Bootstrap** (スタイリング)

## プロジェクト構成

```
Web/
├── backend/                    # Spring Boot バックエンド
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/ecommerce/
│   │   │   │       ├── controller/
│   │   │   │       ├── service/
│   │   │   │       ├── repository/
│   │   │   │       ├── entity/
│   │   │   │       └── config/
│   │   │   └── resources/
│   │   │       ├── application.yml
│   │   │       └── application-dev.yml
│   │   └── test/
│   ├── pom.xml
│   └── README.md
│
├── frontend/                   # React フロントエンド
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│   └── README.md
│
├── README.md
└── .gitignore
```

## セットアップ手順

### 前提条件
- Java 11以上
- Node.js 14以上
- MySQL 8.0以上
- Git

### バックエンド セットアップ

1. **MySQLデータベース作成**
   ```sql
   CREATE DATABASE ecommerce;
   CREATE USER 'ecommerce_user'@'localhost' IDENTIFIED BY 'password';
   GRANT ALL PRIVILEGES ON ecommerce.* TO 'ecommerce_user'@'localhost';
   FLUSH PRIVILEGES;
   ```

2. **バックエンドディレクトリに移動**
   ```bash
   cd backend
   ```

3. **Maven依存関係インストール**
   ```bash
   mvn clean install
   ```

4. **アプリケーション起動**
   ```bash
   mvn spring-boot:run
   ```
   - サーバーは `http://localhost:8080` で起動します

### フロントエンド セットアップ

1. **フロントエンドディレクトリに移動**
   ```bash
   cd frontend
   ```

2. **npm依存関係インストール**
   ```bash
   npm install
   ```

3. **開発サーバー起動**
   ```bash
   npm start
   ```
   - ブラウザは `http://localhost:3000` で自動的に開きます

## API仕様

### 商品API
- `GET /api/products` - 全商品取得
- `GET /api/products/:id` - 商品詳細取得
- `POST /api/products` - 商品作成
- `PUT /api/products/:id` - 商品更新
- `DELETE /api/products/:id` - 商品削除

### 在庫API
- `GET /api/inventory/:productId` - 在庫確認
- `PUT /api/inventory/:productId` - 在庫更新

### 注文API
- `GET /api/orders` - 注文一覧
- `POST /api/orders` - 注文作成
- `GET /api/orders/:id` - 注文詳細

## 開発ワークフロー

1. **ブランチ作成**
   ```bash
   git checkout -b feature/機能名
   ```

2. **コード編集 & コミット**
   ```bash
   git add .
   git commit -m "機能説明"
   ```

3. **プッシュ**
   ```bash
   git push origin feature/機能名
   ```

4. **Pull Request作成**
   - GitHub上でPRを作成してレビューを依頼

## トラブルシューティング

### ポート既に使用中
```bash
# Windows
netstat -ano | findstr :8080
taskkill /PID <PID> /F

# Mac/Linux
lsof -i :8080
kill -9 <PID>
```

### MySQLに接続できない
- MySQLが起動しているか確認
- ユーザー名とパスワード確認
- `application.yml`の接続設定を確認

### Reactが起動しない
```bash
npm cache clean --force
rm -rf node_modules package-lock.json
npm install
npm start
```

## ライセンス

MIT

## 作成者

kei557
