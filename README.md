# README

## users
|column|type  |options|
|------|------|-------|
|name|string|null: false, unique: true,index|
|password|string|null: false|
|email|string|null: false|


### Aassociation
- has_many :messages
- has_many :groups, through: :group_users
- has_many :group_users

## messages
|column|type|options|
|------|----|-------|
|content|text|null: false|
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Aassociation
- belongs_to :user
- belongs_to :group


## groups
|columu|type|options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|


### Aassociation
- has_many :users, through: :group_users
- has_many :group_users
- has_many :messages


## groups_users

|Column|type|options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Aassociation
belongs_to :user
belongs_to :group


