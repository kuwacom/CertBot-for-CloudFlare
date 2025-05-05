# 🚀 CertBot-for-CloudFlare
CloudFlareで管理されているドメインの証明書をCertBotで自動更新

Docker Composeでまとまっているので簡単に利用できます！

---

## 📦 セットアップ手順

### 1. リポジトリをクローン

```bash
git clone https://github.com/kuwacom/CertBot-for-CloudFlare.git
cd　CertBot-for-CloudFlare 
```

### 2. CloudFlareでAPIトークンを作成
CloudFlareにログインしたのちに  
**プロフィール > APIトークン > トークンを作成**  
から、`ゾーン DNS を編集する`のテンプレートを利用して、権限にゾーンDNSの**編集**を付けてください

ゾーンリソースは必要なドメインを設定してください


### 3. トークンを設置
`cloudflare`フォルダ内に`example.ini`をコピーして`cloudflare.ini`を作成して、自身のAPIキーを記入してください

### 4. docker composeファイルを準備
`docker-compose.yaml`をコピーして`docker-compose.<ドメイン名>.yaml`のような、自分のdocker composeファイルを作成します

次に、`--email`オプションに自分のメールアドレスを、`-d`オプションに、証明書に含みたいドメインを記述します  
`-d`オプションは複数設置可能でワイルドカードも利用可能です

### 5. 実行！
あとは`docker compose up`をすることで、自動で証明書類を取得してくれます

結果は`certs`に出力されます