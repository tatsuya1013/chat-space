#DB設計

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|

### Assosiation
- has_many : members
- has_many : messages

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :members
- has_many :messages

##messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|a|
|group_id|integer|null: false ,foreign_key: true|
|user_id|integer|null: false ,foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
