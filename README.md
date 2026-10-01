# お店AI エステサロン向けLP

エステサロン向けLP専用の静的サイトです。既存のお店AIアプリ、`oten-ai` リポジトリ、Vercelプロジェクトとは分けて管理します。

## 公開予定URL

- Preview: `https://<cloudflare-pages-project>.pages.dev/esthetic/`
- Production: `https://lp.omise-ai.com/esthetic/`

## Cloudflare Pages設定

- Project name: `omise-ai-esthetic-lp`
- Build command: 空欄
- Build output directory: `public`
- Production branch: `main`

## DNS設定

Cloudflare Pagesでカスタムドメイン `lp.omise-ai.com` を追加した後、DNS側で以下を設定します。

- Type: `CNAME`
- Name: `lp`
- Target: `omise-ai-esthetic-lp.pages.dev`

Cloudflare公式ドキュメント上、CNAMEを手動追加するだけでは不十分で、Pages側の Custom domains にも対象ドメインを追加する必要があります。

## ローカル確認

```bash
npm run dev
```

表示確認:

- `http://127.0.0.1:8124/esthetic/`
- 予約ボタンが Google Calendar の予約ページへ遷移すること

## 注意

- パスワードやAPIキーはこのリポジトリに入れません。
- 予約URLや料金を変更した場合は、公開前にPC・スマホ表示を確認します。
