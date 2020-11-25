# README

* アプリケーション名
  share photo 

* アプリケーション概要
  写真投稿アプリ

* URL

* テスト用アカウント
  test@test.com

* 利用方法
  アカウント登録により写真の投稿が可能　ログイン時に可能な事:投稿　:削除（投稿し物のみ） :編集（投稿し物のみ）　:コメント　:イイネ機能　未ログイン時可能な事:写真の閲覧のみ 

* 目指した課題解決
  老若男女簡単に使える写真の投稿アプリ。イイネとコメントを付けることにより人気投稿写真をランキングにする機能を実装したい。（予定）ログイン済みユーザーのみ他人の投稿をシェアする機能を実装したい。（予定）

* 洗い出した要件
  https://docs.google.com/spreadsheets/d/12dLKlIwOVi4as5KoTZ6BMMyHic1220AdKCFpMy-6PHw/edit?usp=sharing
  
* 実装した機能についてのGIFと説明

* 実装予定の機能
　アカウント登録機能 ログイン機能　ログアウト機能　投稿機能　編集機能　削除機能　コメント機能  イイネ機能

# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association
* has_many :photo
* has_many :comments

## photo table

| Column                              | Type       | Options           |
|-------------------------------------|------------|-------------------|
| title                               | string     | null: false       |
| concept                             | text       | null: false       |
| user                                | references | foreign_key: true |

### Association
* belongs_to :user
* has_many :comments

## comments table

| Column      | Type       | Options           |
|-------------|------------|-------------------|
| text        | text       | null: false       |
| photo       | references | foreign_key: true |
| user        | references | foreign_key: true |

### Association
* belongs_to :photo
* belongs_to :user

* ローカルでの動作方法