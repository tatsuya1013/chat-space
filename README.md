#DB設計

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false ,unique :true|

### Assosiation
- has_many:groups,through :members
- has_many:members
- has_many: messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false ,unique:true|

### Association
- has_many:users ,through :members
- has_many:users
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|refference :users ,index :ture,foreign_key: true|
|user_id|integer|refference :groups ,index :true,foreign_key: true|

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
