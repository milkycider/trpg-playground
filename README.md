# trpg-playground

個人のTRPGコンテンツ(ツール、クイズなど)をまとめた置き場です。GitHub Pagesで公開します。

## 構成

```
trpg-playground/
├─ index.html          トップページ(各コンテンツへのリンク一覧)
├─ README.md
└─ gender-quiz/
    ├─ index.html          探索者の性別クイズ
    ├─ firebase-config.js  回答の送信先(Firebase)の設定
    └─ admin/
        └─ index.html      回答の集計ページ(管理用)
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

## 性別クイズの回答を集める(任意)

答え合わせを押すと同時に、回答がFirestoreに保存され、共有用のURL(`gender-quiz/?r=<ID>`)が作られます。
Xに共有したURLを開くと、その人の結果(点数と正答率)が表示されます。回答の中身は「この人の回答を見る」を押したときだけ出ます。
`gender-quiz/firebase-config.js` が `null` のままなら、保存も共有URLも無効です。

1. Firebase コンソールでプロジェクトを作り、Firestore Database を作る
2. 「ルール」に、別ファイルの `firestore.rules` の中身を貼って公開する(メールアドレスを自分のものに書き換える)
3. プロジェクトの設定 → マイアプリ → ウェブアプリを追加し、出てきた `firebaseConfig` を `firebase-config.js` に貼る
4. Authentication → ログイン方法で Google を有効にする。設定 → 承認済みドメインに `<ユーザー名>.github.io` を足す
5. push して公開する。全員ぶんの集計は `https://<ユーザー名>.github.io/trpg-playground/gender-quiz/admin/` で、ルールに書いたアカウントでログインして見る

共有URLのIDは推測できない長い文字列です。URLを知っている人は、その結果を開けます。
