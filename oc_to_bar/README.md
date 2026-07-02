# oc_to_bar（金澤）公式LINE 受付ページ

金澤のバー「oc_to_bar」専用の公式LINE案内 ＋ ご予約・お問い合わせフォームの静的ページです。

- 公開URL（GitHub Pages）: `https://isobetadamichi.github.io/bodymente/oc_to_bar/`
- サーバー不要。フォームの送信内容は **公式LINEのトークに本文入りでセットされて送信** されます（`line.me/R/oaMessage` を使用）。

## セットアップ手順（要・人の作業）

公式LINEアカウントの作成はLINEへのログインが必要なため、以下を実施してください。

1. [LINE公式アカウントの開設ページ](https://www.lycbiz.com/jp/service/line-official-account/) から oc_to_bar 専用のアカウントを新規作成する（無料のコミュニケーションプランでOK）。
2. [LINE Official Account Manager](https://manager.line.biz/) にログインし、以下の2つを控える。
   - **ベーシックID**（`@` で始まるID。例 `@012abcde`）… 設定 → アカウント設定
   - **友だち追加URL**（`https://lin.ee/…`）… 友だちを増やす → 友だち追加ガイド
3. `oc_to_bar/index.html` の冒頭にある `CONFIG` を書き換える。

```js
const CONFIG = {
  LINE_OA_ID: "@012abcde",              // ← ベーシックID
  ADD_FRIEND_URL: "https://lin.ee/xxxxxxx" // ← 友だち追加URL
};
```

4. コミットしてpushすると、GitHub Pagesに反映されます。

## 設定後の動き

- **STEP 1**: 友だち追加ボタン／QRコード（友だち追加URLから自動生成）を表示。
- **STEP 2**: フォーム送信でLINEアプリが開き、入力内容（ご用件・お名前・希望日時・人数など）がトークにプリセットされる。ユーザーはそのまま送信するだけ。
- LINEが開けない環境向けに「入力内容をコピー」ボタンあり。
- `CONFIG` が未設定の間は、ページ上部に管理者向けの警告バナーが表示され、フォームはコピー動作にフォールバックします。

## おすすめの公式LINE側設定

- **あいさつメッセージ**にこのページのURLを入れる（友だち追加直後にフォームへ誘導できる）。
- **リッチメニュー**に「ご予約フォーム」ボタンを作り、このページのURLをリンクする。
