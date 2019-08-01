---
layout: default
title: Creating your first TuxJSQL
nav_order: 4
---

# Step one creating a Properties.
TuxJSQL uses Properties to get its required arguments.
Each TuxJSQL dialect has a different set of values so you need to check that dialects required values.

However, every TuxJSQL properties needs this value `db.type` this points to a specific class check your dialects docs for this class path.

We also have an optional value. `executors.count` this is an integer and this sets the number of executors in the Thread pool. by default its 1.

## Connection Providers
Connection providers may also have optional values. so please check the docs on this specific CP
# Example time

```java
import java.util.Properties;

public class Main {
    public static void main(String[] args) {
        Properties properties = new Properties();
        properties.setProperty("db.type", "dev.tuxjsql.sqlite.SQLiteBuilder");
        //SQLite requires a file
        properties.setProperty("db.file", "db.db");
        properties.setProperty("executors.count", "3");
        TuxJSQL tuxJSQL =  TuxJSQLBuilder.create(properties);

    }
}
```
