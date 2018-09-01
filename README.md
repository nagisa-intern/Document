# Table構成

## comics

作品情報

| column | type | NOT NULL | comment | PRIMARY KEY |
| :---: | :---: | :---: | :---:| :----: |
| id | INT | true | 作品ID | true |
| title | VARCHAR(255) | true | 作品タイトル | false |
| summary | Text | true | 作品説明文 | false |

## authors

著者情報

| column | type | NOT NULL | comment | PRIMARY KEY |
| :---: | :---: | :---: | :---:| :----: |
| id | INT | true | 作者ID | true |
| name | VARCHAR(255) | true | 作者名 | false |
| info | Text | true | 作者紹介文 | false |

## comic_data

作品の話ごとの情報

| column | type | NOT NULL | comment | PRIMARY KEY | 備考 |
| :---: | :---: | :---: | :---:| :----: | :---: |
| id | INT | true | 作品データid | true | |
| comic_id | INT | true | 作品id | false | 外部key comic(id) |
| title | VARCHAR(255) | true | 作品データタイトル | false | |
| episode | INT | false | 話数 | false | |

## comic_author

作品と作者の中間テーブル

| column | type | NOT NULL | comment | PRIMARY KEY | 備考 |
| :---: | :---: | :---: | :---:| :----: | :---: |
| comic_id | INT | true | 作品id | false | 外部key comic(id) |
| author_id | INT | true | 作者id | false | 外部key author(id)|

# 画像情報

## 作品画像

### サムネイル

![sample](https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/1/thumb.jpeg)

format: "https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/#{comic.id}/thumb.jpeg"

sample: "https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/1/thumb.jpeg"

### 正方形

![sample](https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/1/square_thumb.jpeg)

format: "https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/#{comic.id}/square_thumb.jpeg"

sample: "https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/1/square_thumb.jpeg"

### 長方形

![sample](https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/1/rec_thumb.jpeg)

format: "https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/#{comic.id}/rec_thumb.jpeg"

sample: "https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/comic/1/rec_thumb.jpeg"

## 作者アイコン

![sample](https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/author/1/icon.jpeg)

format: https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/author/#{author.id}/icon.jpeg

sample: https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/author/1/icon.jpeg

## 作品の話ごとのデータ

### 表紙

### １ページ毎

![sample](https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/data/1/1/0000.jpeg)

format: https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/data/#{comic.id}/#{comic_data.episode}/#{ページ数を0を4つ詰め}.jpeg


sample: https://s3-ap-northeast-1.amazonaws.com/nagisa-intern/data/1/1/0000.jpeg
