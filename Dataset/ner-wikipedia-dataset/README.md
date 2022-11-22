# Wikipediaを用いた日本語の固有表現抽出データセット

**Version: 2.0**

## 概要

このデータセットはWikipediaから抜き出した文に対して、固有表現をタグ付けしたものです。固有表現をハイライトしたサンプルは[こちら](https://stockmarkteam.github.io/ner-wikipedia-dataset/index.html)でご覧になれます。全データ数は5343で、各データは一文から構成されています。全体の10%程度が固有表現を含まない負例です。このデータセットでタグ付された固有表現のタイプと、それぞれのタイプごとの固有表現数は以下の表にまとめられます。

|タイプ|固有表現数|備考|
|:--|:--:|:--|
|人名|2980||
|法人名|2485|法人または法人に類する組織|
|政治的組織名|1180|政治的組織名、政党名、政府組織名、行政組織名、軍隊名、国際組織名|
|その他の組織名|1051|競技組織名、公演組織名、その他|
|地名|2157||
|施設名|1108||
|製品名|1215|商品名、番組名、映画名、書籍名、歌名、ブランド名等|
|イベント名|1009||

## データ形式

データファイル: ner.json

データファイルはjson形式で、全体としてはデータサンプルのリストとして構成されています。各データは以下のような辞書形式です。

```
{
    "curid": "473536",
    "text": "イギリスはリーマンショック直後の2008年10月にイングランド銀行のバランスシートを一気に3倍近く増やした後、2008年11月から2009年3月にかけて段階的に縮小させていった。",
    "entities": [
        {
            "name": "イギリス",
            "span": [0,4],
            "type": "地名"
        },
        {
            "name": "リーマンショック",
            "span": [5,13],
            "type": "イベント名"
        },
        {
            "name": "イングランド銀行",
            "span": [25,33],
            "type": "政治的組織名"
        }
    ]
}
```

- curidはデータ元のWikipediaのページID
- textはタグ付を行う対象のテキスト
- entitiesは固有表現のリスト
    - nameは固有表現名
    - spanはtextでの位置
    - typeは固有表現のタイプ

## ライセンス

Wikipedia日本語版と同じCC-BY-SA 3.0のライセンスに従います。（参考：[Wikipediaの著作権](https://ja.wikipedia.org/wiki/Wikipedia:%E8%91%97%E4%BD%9C%E6%A8%A9)）

商用利用も可能です。

このデータセットを改変・再配布される方は、Wikipediaの[こちら](https://ja.wikipedia.org/wiki/Wikipedia:%E3%82%A6%E3%82%A3%E3%82%AD%E3%83%9A%E3%83%87%E3%82%A3%E3%82%A2%E3%82%92%E4%BA%8C%E6%AC%A1%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B)のページを参考にしてください。

## 参考文献

近江崇宏、「Wikipediaを用いた日本語の固有表現抽出のデータセットの構築」、言語処理学会 第27回年次大会（2021）[PDF](https://anlp.jp/proceedings/annual_meeting/2021/pdf_dir/P2-7.pdf)

## 作成

本データセットはストックマーク株式会社により作成されました。
https://stockmark.co.jp/