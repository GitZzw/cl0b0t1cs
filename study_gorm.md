## GORM

#### 安装翻墙问题
https://blog.csdn.net/fly910905/article/details/104255701

#### gorm连接数据库
>> https://learnku.com/docs/gorm/v2/connecting_to_the_database/9731
GORM 官方支持的数据库类型有： MySQL, PostgreSQL, SQlite, SQL Server

```
import (
  "gorm.io/driver/mysql"
  "gorm.io/gorm"
)

func main() {
  // 参考 https://github.com/go-sql-driver/mysql#dsn-data-source-name DSN (Data Source Name)
  // 完整形式的ds:=username:password@protocol(address)/dbname?param=value
  // 除了数据库名称以外其他的都是可选项 最小的dsn:="dbname"
  dsn := "user:pass@tcp(127.0.0.1:3306)/dbname?charset=utf8mb4&parseTime=True&loc=Local"
  db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{})
}
```


#### CURD接口
>> https://learnku.com/docs/gorm/v2/create/9732

创建记录
```
user := User{Name: "Jinzhu", Age: 18, Birthday: time.Now()}

result := db.Create(&user) // 通过数据的指针来创建

user.ID             // 返回插入数据的主键
result.Error        // 返回 error
result.RowsAffected // 返回插入记录的条数
```
