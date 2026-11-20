# trpg-playground

個人のTRPGコンテンツ(ツール、クイズなど)をまとめた置き場です。GitHub Pagesで公開します。

## 構成

```
trpg-playground/
├─ index.html          トップページ(各コンテンツへのリンク一覧)
├─ README.md
└─ gender-quiz/
    └─ index.html      探索者の性別クイズ
```

コンテンツごとにフォルダを作り、中身を `index.html` にします。
公開URLは `https://<ユーザー名>.github.io/trpg-playground/<フォルダ名>/` になります。

## 公開手順

1. このフォルダの中身をリポジトリ `trpg-playground` に置いて push する
2. リポジトリの Settings → Pages を開く
3. Source を「Deploy from a branch」、Branch を `main`、フォルダを `/ (root)` にして保存する
4. 数分後に `https://<ユーザー名>.github.io/trpg-playground/` で開ける

## コンテンツを足すとき

1. 英小文字とハイフンでフォルダ名を決める(例: `my-tool`)
2. その中に `index.html` を置く
3. トップの `index.html` に、リンクのカードを1つ足す

## 注意

- 公開すると、URLを知っている人は誰でも開けます。ページのソースを見れば、クイズの答えも読めます。
- 各ページには `<meta name="robots" content="noindex">` を入れています。検索エンジンに載りにくくなりますが、見られないようにするものではありません。
- シナリオのネタバレになるデータは置かないでください。
