# お店AI エステサロン向けLP

エステサロン向けLP専用の静的サイトです。既存のお店AIアプリ、`oten-ai` リポジトリ、Vercelプロジェクトとは分けて管理します。

## 公開予定URL

- Preview: `https://omise-ai-esthetic-lp.pages.dev/esthetic/`
- Production: `https://lp.omise-ai.com/esthetic/`
- GitHub: `https://github.com/omise-ai-kentaro/omise-ai-esthetic-lp`

## Cloudflare Pages設定

- Project name: `omise-ai-esthetic-lp`
- Framework preset: None
- Build command: 空欄
- Build output directory: `public`
- Production branch: `main`
- Git integration: the GitHub repository above

Cloudflare Pages must be selected as the platform. The Wrangler configuration uses `pages_build_output_dir`; do not run `wrangler deploy`, which deploys a Worker with static assets instead of this Pages project.

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

Pages runtime preview:

```bash
npm run preview
```

This serves the Pages project locally. It does not publish or change Cloudflare resources.

## 注意

- パスワードやAPIキーはこのリポジトリに入れません。
- 予約URLや料金を変更した場合は、公開前にPC・スマホ表示を確認します。
