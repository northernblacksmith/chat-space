# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


## usersテーブル
|column|type|options|
|------|----|-------|
|name|string|null :false, foreign_key: true|
|mail|string|null :false, foreign_key: true|
|group_id|integer|null :false, foreign_key: true|

### Association
-has_many :messages
-has_many :groups, through :members

## groupsテーブル
|column|type|options|
|------|----|-------|
|group_name|string|null :false, foreign_key: true|
|members_id|integer|null :false, foreign_key: true|
|messages|string|null :false, foreign_key: true|

### Association
-has_many :users, through :members
-has_many :messages

## membersテーブル
|column|type|options|
|------|----|-------|
|user_id|integer|null :false, foreign_key: true|
|group_id|integer|null :false, foreign_key: true|

### Association
-belongs_to :group
-belongs_to :user


## messagesテーブル
|column|type|options|
|------|----|-------|
|member_id|integer|null :false, foreign_key: true|
|message|string|null :false, foreign_key: true|
|created_at|timestamp|null :false, foreign_key: true|

### Association
-belongs_to :user, through :member
-belongs_to :group, through :member




