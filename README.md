## usersテーブル
| columns    | types    | options  |
| ---------- | -------- | -------  |
| email      | string   | NOT NULL |
| password   | string   | NOT NULL |
| name       | string   | NOT NULL |
| profile    | text     | NOT NULL |
| occupation | text     | NOT NULL |
| position   | text     | NOT NULL |

### Association
- belongs_to: comments
- belongs_to: prototypes


## prototypesテーブル
| columns    | types      | options  |
| ---------- | ---------- | -------- |
| title      | string     | NOT NULL |
| catch_copy | text       | NOT NULL |
| concept    | text       | NOT NULL |
| user       | references |          |

### Association
- belongs_to: comments
- has_many: users

## commentsテーブル
| columns   | type       | option   |
| --------- | ---------- | -------- |
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

### Association
- has_many: users
- has_many: prototypes
