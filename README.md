# クリエイティブ知識ベース

Meta広告クリエイティブの分析結果を蓄積・共有する社内ナレッジツール。  
「媒体 × 広告目的 × ジャンル」で分類し、月次分析の知見をチームで活用する。

---

## アクセス

**[→ ツールを開く](https://adig-inc.github.io/creative-knowledge-base/)**

- Googleアカウントでのログインが必須
- アクセスは許可リストに登録されたメールアドレスのみ

---

## 主な機能

| タブ | 内容 |
|------|------|
| 新規登録 | 月次のMeta広告分析後に知見を登録 |
| 知識ベース一覧 | 媒体・目的・ジャンル・キーワードでフィルタリング |
| エクスポート | プロンプト挿入用 / Markdown / JSONバックアップ で出力 |

---

## 構成

```
index.html        ← フロントエンド（このリポジトリ、GitHub Pagesで配信）
GAS / Sheets      ← バックエンド・データベース（ADIGのGoogleアカウントで管理）
```

データはすべてGoogleスプレッドシートに保存されます。このリポジトリにデータは含まれません。

---

## アクセス管理

GASエディタから以下の関数を実行するだけで管理できます（再デプロイ不要）。

```javascript
addToAllowlist("member@gmail.com")      // メンバー・クライアントを追加
removeFromAllowlist("exmember@gmail.com") // アクセスを削除
getAllowlist()                           // 現在のリストを確認
```

---

## 初回セットアップ（新しいPCや引き継ぎ時）

1. [ツールのURL](https://adig-inc.github.io/creative-knowledge-base/) を開く
2. セットアップ画面でGASデプロイURLとOAuthクライアントIDを入力
3. 「保存して続ける」→ Googleアカウントでログイン

> GASデプロイURL・OAuthクライアントIDはADIG管理者に確認してください。

---

## 管理者向け情報

詳細なセットアップ手順・仕様は [仕様書.md](仕様書.md) を参照してください。

- **GAS・スプレッドシート**：ADIGのGoogleアカウントで管理
- **OAuthクライアントID**：Google Cloud Console（個人アカウント）で管理
- **GASを再デプロイした場合**：デプロイURLが変わるため、各自の設定更新が必要
