## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|image|string||
|content|string||
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
## Association
- belongs_to :user
- belongs_to :group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
### Association
- has_many :users, through: :groups_users
- has_many :messages
- has_many :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

&__text {
    font-size: 14px;
    color: #434A54;
    margin-top: 12px;
  }
  &__upper-info {
  display: flex;
  &__talker {
    font-size: 16px;
    color: #333333;
  }
  &__date {
    font-size: 12px;
    color: $mainGrayColor;
  }
}