#テーブル設計

## users　テーブル

| Column     | Type   | Options     | 
| ---------- | ------ | ----------- | 
| email      | string | null: false | 
| password   | string | null: false | 
| nickname   | string | null: false | 


### Association
 - has_many :comments
 - has_many :items

## items　テーブル

| Column      | Type       | Options                        | 
| ----------- | ---------- | ------------------------------ | 
| title       | string     | null: false                    | 
| genre       | integer    | null: false                    | 
| discription | text       | null: false                    | 
| image       |            |                                | 
| company     | integer    | null: false                    |
| user        | references | null: false, foreign_key: true | 

### Association
 - has_many :comments
 - belongs_to :user

## comments　テーブル

| Column | Type       | Options                        | 
| ------ | ---------- | ------------------------------ | 
| text   | text       | null: false                    | 
| user   | references | null: false, foreign_key: true | 
| item   | references | null: false, foreign_key: true | 

### Association
  - belongs_to :user
  - belongs_to :item

