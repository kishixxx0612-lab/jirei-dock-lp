# 事例ドック LP

事例ドックの問い合わせ獲得用ランディングページです。HTML/CSS/JS の1ファイル構成（画像のみ `images/` に分離）で、GitHub Pages でそのまま公開できます。

## ファイル構成

```
.
├── index.html     # LP本体（HTML / CSS / JS）
├── thanks.html    # 問い合わせ完了ページ（noindex）
├── images/        # ヒーロー画像・お悩みカード画像
├── .nojekyll      # GitHub Pages の Jekyll 処理を無効化
└── README.md
```

## ローカルで確認する

```bash
npx http-server -p 3004 -c-1 .
```

ブラウザで http://localhost:3004 を開きます。

## GitHub Pages で公開する

1. GitHub で新しいリポジトリを作成する（例：`jirei-dock-lp`）
2. このフォルダをリポジトリに push する

   ```bash
   git remote add origin https://github.com/kishixxx0612-lab/jirei-dock-lp.git
   git push -u origin main
   ```

3. リポジトリの **Settings → Pages** を開き、
   **Source: Deploy from a branch** ／ **Branch: `main`** ／ **Folder: `/ (root)`** を選んで Save
4. 1〜2分後に https://kishixxx0612-lab.github.io/jirei-dock-lp/ で公開されます

## 公開前のチェックリスト

- [ ] フォーム送信を有効化する（下記「お問い合わせフォーム」参照）
- [ ] HTML内の `<!-- 要確認 -->` 箇所の文言を原文と照合する

## お問い合わせフォーム

フォームの内容は [FormSubmit](https://formsubmit.co/) を経由して `jirei.dock@gmail.com` にメールで届きます（サーバー不要・無料）。
送信に成功すると `thanks.html` に移動します。

### 初回だけ必要な有効化

1. 公開後のページからフォームを1回送信する
2. `jirei.dock@gmail.com` に FormSubmit から確認メール（件名：Action Required: Activate FormSubmit）が届く
3. メール内の **Activate Form** をクリックする

有効化するまでは問い合わせ内容は届きません。有効化後に、もう一度テスト送信して受信を確認してください。

### 送信先アドレスを隠す（任意）

有効化メールに記載されるランダム文字列のアドレスを使うと、ソースコードにメールアドレスを載せずに済みます。
`index.html` の `FORM_ACTION` を `https://formsubmit.co/ajax/（ランダム文字列）` に置き換えてください。
