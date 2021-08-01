# DB 設計

## users table

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| nickname           | string              | null: false               |
| email              | string              | null: false, unique: true |
| encrypted_password | string              | null: false               |
| birth              | date                | null: false               |
| profile            | text                | null: false               |

### Association
* has_many :posts
* has_many :comments

## posts table

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| title              | string              | null: false               |
| catch_copy         | text                | null: false               |
| concept            | text                | null: false               |
| user               | references          | foreign_key: true         |

### Association
- belongs_to :user
- has_many :comments

## comments table

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| text               | text                | null: false               |
| post               | references          | foreign_key: true         |
| user               | references          | foreign_key: true         |

### Association
- belongs_to :post
- belongs_to :user
