# genre.ini の使い方

フォルダの名前・色・見出し・画像を設定できます。設定したいフォルダに `genre.ini` を置き、必要な項目だけ記入してください。

## 基本の例

```ini
GenreName=おすすめ譜面
GenreColor=#2985c2
FontColor=#ffffff
GenreIcon=preset:drum
GenreHeader=1
GenreSubtitle=好きな曲から遊んでください
GenreDescription=さまざまな難易度を収録しています。
```

編集後は、Re:JIROのライブラリを再読み込みしてください。

## 設定項目

| 項目 | 内容・例 |
| --- | --- |
| `GenreName` | フォルダの表示名 |
| `GenreColor` | フォルダの色。例：`#2985c2` |
| `FontColor` | 文字色。例：`#ffffff` |
| `GenreIcon` | アイコン。例：`preset:drum`（太鼓）、`preset:music`（音符）、`preset:star`（星） |
| `GenreOrder` | フォルダの並び順。小さい数字が先です |
| `GenreSubtitle` | 見出しのサブタイトル |
| `GenreDescription` | 見出しの説明文。改行は `\n` と書きます |
| `GenreMaker` | 見出しに表示する譜面制作者名 |
| `GenreHeader` | 見出しを表示するなら `1`、隠すなら `0` |
| `GenreHeaderSubfolders` | 下位フォルダにも見出し設定を使うなら `1`。既定はオフです |
| `GenreHeaderKeepName` | 下位でも親の見出し名を使うなら `1`、開いたフォルダ名を使うなら `0`。既定は `1` です |
| `GenreImage` | フォルダの行・ボタンの背景画像 |
| `GenreHeaderImage` | 見出しの背景画像 |
| `GenreCover` | ジャケット画像 |
| `GenreBackground` | 演奏画面の背景画像 |
| `GenreGradient` | 背景のグラデーション。例：`#2985c2,#267a62` |
| `GenreGradientAngle` | グラデーションの角度。例：`90` |

## 下位フォルダにも同じ見出しを使う

親フォルダの設定に、次の2行を追加します。

```ini
GenreHeaderSubfolders=1
GenreHeaderKeepName=1
```

下位フォルダでも親の見出し名が表示されます。名前だけ各フォルダに合わせたい場合は、`GenreHeaderKeepName=0` にします。

子フォルダ自身に設定した説明文などは、親の設定より優先されます。そのフォルダだけ見出しを隠す場合は `GenreHeader=0` にしてください。

## 画像を使う

画像は `genre.ini` と同じフォルダ、またはその下に置きます。

```text
譜面パック/
  genre.ini
  images/
    header.png
    cover.png
```

```ini
GenreHeaderImage=images/header.png
GenreCover=images/cover.png
```

PNG・JPG／JPEG・WebP・GIF・AVIFに対応しています。絶対パス・外部URL・`../` は使えません。アプリ側で個別設定したジャケット・背景画像がある場合は、そちらが優先されます。

## 困ったときは

- **見出しが出ない：** `GenreHeader=1` を指定し、ライブラリを再読み込みしてください。
- **見出しの位置を変えたい：** 設定 → テーマ → 選曲画面 → 一覧表示 → フォルダの見出しで切り替えます。未設定時はナビゲーションバーと統合します。
- **文字化けする：** 新規作成はUTF-8を推奨します。既存のShift_JISにも対応しています。

`GenreName`・`GenreColor`・`FontColor` 以外はRe:JIRO独自の項目です。他のプレイヤーで同じ表示になるとは限りません。
