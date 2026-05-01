# 席替えシート

ブラウザだけで名簿（Excel）から席替えを行えるシンプルなウェブアプリです。サーバ不要、静的ホスティングで公開できます。

---

## 構成

```
/  (プロジェクトルート)
├─ assets/
│  ├─ roster_template.xlsx
│  ├─ roster_template_sample.xlsx
│  ├─ 名簿テンプレート.xlsx
│  ├─ 名簿テンプレート_授業用.xlsx
│  ├─ icon-192.png        (任意: PWA用アイコン)
│  └─ icon-512.png        (任意: PWA用アイコン)
├─ lib/
│  └─ xlsx.full.min.js    (SheetJS等)
├─ seat.html              (席替え画面)
├─ setup.html             (使い方/導線/テンプレDL)
├─ privacy.html           (このファイルで生成)
├─ manifest.json          (PWA用)
└─ robots.txt
```

> 注: `lib/xlsx.full.min.js` の拡張子`.js`を付けてください。

---

## 公開方法（GitHub なし、完全無料）

### 1) Netlify Drop（最短・無料）
1. ビルド不要の本プロジェクトフォルダを ZIP 化
2. https://app.netlify.com/drop にアクセス
3. ZIP をドラッグ&ドロップ → 即座に `https://<auto-id>.netlify.app` で公開
4. 更新は同じ手順で再アップロード

### 2) Cloudflare Pages（GitHub なしでも可: Direct Upload）
- Cloudflare アカウント作成 → Pages → **Direct Upload**（プロジェクトを新規作成してローカルからアップロード）
- または GitHub を作成・接続して自動デプロイ

### 3) GitHub を使う場合（任意）
1. GitHub アカウント作成 → 新規リポジトリ
2. 既存フォルダをコミット&プッシュ
3. Cloudflare Pages / Netlify / Vercel と連携して自動デプロイ

---

## 設定（広告・計測・同意）

### Google AdSense（広告）
1. AdSense にサイト登録・審査
2. 承認後、`setup.html` の `<head>` にクライアントID付きのスクリプトを貼り付け
3. ページ内に広告枠（`<ins class="adsbygoogle">`）を配置

### Google Analytics 4（GA4）
- 計測ID (`G-XXXXXXX`) を発行して `setup.html` / `seat.html` に設置
- ダウンロード・開始ボタンなどはイベント送信

### 同意管理（CMP）
- CookieYes / Quantcast Choice / Google Funding Choices などの無料CMPを導入
- Consent Mode v2 を有効化して、同意に応じてタグを制御

---

## セキュリティ/プライバシーの注意
- 名簿ファイルはブラウザ内処理（サーバ送信なし）にしてください
- HTTPS で配信（Netlify/Cloudflare は自動）
- プライバシーポリシー（`privacy.html`）とフッターリンクを設置

---

## 開発メモ
- 主要ブラウザでの動作確認（PC/スマホ）
- 例外処理：`xlsx.full.min.js` ロード失敗時のユーザ通知
- PWA 化する場合は Service Worker を追加

---

## ライセンス
- テンプレートやライブラリのライセンス条件に従ってください

