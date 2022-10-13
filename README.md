# DB設計

## users　テーブル

|Column            |Type       |Option       |


|email             |string     |null: false    |
|encrypted_password|string     |null: false    |
|name              |string     |null: false    |
|profile           |text       |null: false    |
|occupation        |text       |null: false    |
|position          |text       |null: false    |

### association

* has_many :prototypes
* has_many :comments

## prototyqes テーブル

|Column            |Type       |Options      |

|title             |string     |null: false    |
|catch_copy        |text       |null: false    |
|concept           |text       |null: false    |
|user              |references |null: false, foreign_key:true   |

### association

* belongs_to :user
* has_many :comments


## comments テーブル

|Column             |Type       |Options      |

|content            |text       |null: false    |
|prototype          |references |null: false, foreign_key: true |
|user               |references |null:false, foreign_key: true  |

### association

* belongs_to :prototype
* belongs_to :user