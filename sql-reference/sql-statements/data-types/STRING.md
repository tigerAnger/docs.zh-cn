# STRING

## 描述

STRING

变长字符串，最大长度 65533 字节。

## 示例

创建表时指定字段类型为 STRING。

```sql
CREATE TABLE stringDemo (
    pk INT COMMENT "range [-2147483648, 2147483647]",
    us_detail STRING COMMENT "upper limit value 65533 bytes"
) ENGINE=OLAP 
DUPLICATE KEY(pk)
COMMENT "OLAP"
DISTRIBUTED BY HASH(pk) BUCKETS 4;
```

表创建成功后通过 `desc tablename;` 查看表可以看到 STRING 类型为 `VARCHAR(65533)`。StarRocks 2.1 版本之后大字符串支持到 1MB。
