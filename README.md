# -
電線管の占積率、ケーブルのサイズを選定
# 電線管選定シミュレーター（PWA版）

スマホのホーム画面に追加すると、圏外でもアプリとして起動できる版です。

## ファイル構成

```
index.html              本体
manifest.webmanifest    アプリ情報（名前・アイコン・全画面表示）
sw.js                   オフライン用の保存処理（Service Worker）
icons/                  アプリアイコン
README.md               この説明書
```

フォルダ構成を変えずに、そのままアップロードしてください。

## GitHub Pages での公開手順

1. https://github.com でアカウントを作成（無料）してログイン
2. 右上の「＋」→「New repository」
   - Repository name：例 `conduit-sim`（半角英数字）
   - 「Public」を選択 → 「Create repository」
3. 作成した画面の「uploading an existing file」をクリック
4. このZIPを解凍した中身（index.html、sw.js、manifest.webmanifest、iconsフォルダ）をまとめてドラッグ＆ドロップ
   → 下の「Commit changes」
5. リポジトリの「Settings」→ 左メニュー「Pages」
   - Source：「Deploy from a branch」
   - Branch：「main」「/(root)」→「Save」
6. 1〜2分待つと、同じ画面に公開URLが表示されます
   `https://（ユーザー名）.github.io/conduit-sim/`

※ Publicリポジトリなので、URLを知っている人は誰でも開けます（中身は計算ツールのみで、入力データはサーバーに送られません）。

## スマホへのインストール

**iPhone（Safari）**
1. 公開URLをSafariで開く
2. 下の共有ボタン（□↑）→「ホーム画面に追加」→「追加」

**Android（Chrome）**
1. 公開URLをChromeで開く
2. 右上「⋮」→「アプリをインストール」（または「ホーム画面に追加」）

一度ネットにつながった状態で開けば、その後は圏外でも起動できます。

## 更新するとき

1. 新しい index.html をGitHubに上書きアップロード
2. **sw.js の `CACHE_VERSION = 'v1'` を `'v2'` のように1つ上げて**一緒にアップロード
3. スマホでネットにつながった状態でアプリを開く → 自動的に新しい版に切り替わります
   （切り替わらない場合は、アプリを一度閉じて開き直してください）

## 入力データについて

- 選んだ電線管・ケーブルは端末内（ブラウザの保存領域）に自動保存されます
- iPhoneでは、ホーム画面のアプリとSafariで開いたページの保存データは別になります
- アプリを削除すると保存データも消えます
