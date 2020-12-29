# 開発要件

## appname
- 

## ペルソナ
- 性別：問わない
- 職業：問わない
- 趣味：サブカルチャー、アート観賞、変わった物が好き、アニメ・漫画、ゲーム
- 日頃の生活：学生、社会人

## アプリケーション概要
- 因幡都頼による作品を素材にしたゲームをプラットフォームに、「実際の作品を見てみたい。」と感じさせ展示会などに足を運んでもらう。
- artに興味を持ってもらうための導入としてゲーム性のあるアプリケーションを作成する。

## URL
-

## テストアカウント
-

## 利用方法
- 

## 目指した課題解決
- artをもっと

## 洗い出した要件
-

## 機能についてのGIFと説明
-
-

## 実装予定の機能
-
-

## ローカルでの動作方法
-


# テーブル設計

## users テーブル

| Column             | Type   | Option                    |
| ------------------ | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |

### Association
- has_one : scores
- has_one : gameids
## gameid

| Column  | Type      | Option            |
| ------- | --------- | ----------------- |
| user_id | reference | foreign_key: true |

### Association
has_one  : scores
has_one  : users

## scores テーブル

| Column             | Type      | Option            |
| -----------------  | --------- | ----------------- |
| user_id            | reference | foreign_key: true |
| score              | integer   | null: false       |
| game_id            | reference | foreign_key: true |

### Association

- has_one :users
- has_one :gameid