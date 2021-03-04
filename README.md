# BANTED


## 概要
このアプリはバンドメンバーの募集をすることができます。
投稿された募集に対してユーザーはコメントをしたりいいねをすることもできます。

## 制作意図
社会人になってからバンドを組んで演奏したり、近くで気の合うメンバーを探すのが困難な状況なのでこれらを解消するために制作しました。
　また、昨今はオンラインセッションというものができておりその募集をもできるようにする。

## 実装予定の機能
+ 募集文の投稿
+ マイページ機能
+ ユーザー情報の編集

# DB設計
## usersテーブル

|  Column           |  Type       |  Options            |
|  ---------------  |  ---------  |  ------------       |
|  email            |  string     |  null:  false       |
|  password         |  string     |  null:  false       |
|  nickname         |  string     |  null:  false       |
|  age              |  integer    |  null:  false       |
|  area             |  string     |  null:  false       |
|  instrument       |  string     |  null:  false       | 
|  gender_id        |  integer    |  null:  false       |
|  direction_id     |  integer    |  null:  false       |
|  profile          |  text       |  null:  false       |

+ has_many :recruits
+ has_many :comments


## recruitsテーブル

|  Column           |  Type       |  Options            |
|  ---------------  |  ---------  |  ------------       |
|  title            |  text       |  null:  false       |
|  text             |  text       |  null:  false       |
|  instrument       |  string     |  null:  false       |
|  direction_id     |  integer    |  null:  false       |
|  area             |  string     |  null:  false       |
|  frequency        |  string     |  null:  false       | 
|  user             |  reference  |  foreign_key: true  |

+ has_many :comments
+ belongs_to :user

## commentsテーブル

|  Column           |  Type       |  Options            |
|  ---------------  |  ---------  |  ------------       |
|  text             |  text       |  null:  false       |
|  user             |  reference  |  foreign_key: true  |
|  recruit          |  reference  |  foreign_key: true  |

+ belongs_to :user
+ belongs_to :recruit



