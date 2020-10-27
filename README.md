usersテーブル

| Columns     | Typs        | Option           |
| ----------- |------------ | -----------------|
| email       |   string    | null: false      |
| password    |   string    | null: false      |
| name        |   string    | null: false      |
| profile     |   text      | null: false      |
| occupation  |   text      | null: false      |
| position    |   text      | null: false      |

Association
has_many :comments
has_many :prototypes


prototypsテーブル

| Columns     | Typs              | Option                              |
| ----------- |-------------------| ------------------------------------|
| title       |   string          | null: false                         |
| catch_copy  |   text            | null: false                         |
| concept     |   text            | null: false                         |
| user        |   references      | null: false, foreign_key: true      |
| image       |   activeStorage   |                                     |

Association
belongs_to :user
has_many :comments


commentsテーブル

| Columns     | Typs              | Option                              |
| ----------- |-------------------| ------------------------------------|
| text        |   text            | null: false                         |
| user        |   references      | null: false, foreign_key: true      |
| prototypes  |   references      | null: false, foreign_key: true      |

Association
belongs_to :user
belongs_to :prototype

