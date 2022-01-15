# users　テーブル（ユーザー情報）
| Colum              | Type       | Options                        |
|--------------------|------------|--------------------------------|
| nickname           | string     | null: false                    |
| encrypted_password | string     | null: false                    |
| email              | string     | null: false, unique: true      |
| first_name         | string     | null: false                    |
| last_name          | string     | null: false                    |
| kfirst_name        | string     | null: false                    |
| klast_name         | string     | null: false                    |
| birthday           | date       | null: false                    |

### Association
has_many :requests
has_many :posts

## requests テーブル（投稿内容）
| Colum              | Type       | Option                         |
|------------------- |------------|------------------------------  |
| name               | string     | null: false                    |
| area_id            | integer    | null: false                    |
| type_id            | integer    | null: false                    |
| category_id        | integer    | null: false                    |
| explain            | text       | null: false                    |
| old_id             | integer    | null: false                    |
| period_id          | integer    | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association
belongs_to :user
has_one :comment


## companies テーブル （会社情報）
| Colum              | Type       | Option                         |
|------------------  |------------|--------------------------------|
| c_name             | string     | null: false                    |
| encrypted_password | string     | null: false                    |
| email              | string     | null: false, unique: true      |
| postal             | string     | null: false                    |
| area_id            | integer    | null: false                    |
| city               | string     | null: false                    |
| address             | string     | null: false                    |
| building           | string     | null: false                    |
| tel                | integer    | null: false                    |
| promotion          | text       | null: false                    |
| url                | text       | null: false                    |

### Association
has_many comments
has_one posts


## comments テーブル　（コメント）
| Colum              | Type       | Option                         |
|------------------  |------------|--------------------------------|
| reply              | text       | null: false                    |
| company            | references | null: false                    |

### Association
belongs_to :company
belongs_to :request

## posts テーブル　（会社評価）
| Colum              | Type       | Option                         |
|------------------  |------------|--------------------------------|
| evaluation         | float      | null: false                    |
| review             | text       |                                |
| user               | references | null: false                    |

### Association
belongs_to :company
belongs_to :request

