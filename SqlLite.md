## SQLite Database

SQLite is a lightweight and embedded database engine used in Android to store data locally. Here are some examples of how to work with SQLite in Android:

1. SQLite Database:

To work with SQLite in Android, you need to create a SQLite database using the `SQLiteOpenHelper` class. Here's an example of how to create a database:

```
public class MyDatabaseHelper extends SQLiteOpenHelper {

    private static final String DATABASE_NAME = "my_database.db";
    private static final int DATABASE_VERSION = 1;

    public MyDatabaseHelper(Context context) {
        super(context, DATABASE_NAME, null, DATABASE_VERSION);
    }

    @Override
    public void onCreate(SQLiteDatabase db) {
        String sql = "CREATE TABLE my_table ("
                + "id INTEGER PRIMARY KEY AUTOINCREMENT,"
                + "name TEXT,"
                + "age INTEGER)";
        db.execSQL(sql);
    }

    @Override
    public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {
        String sql = "DROP TABLE IF EXISTS my_table";
        db.execSQL(sql);
        onCreate(db);
    }
}
```

In the above example, we create a `MyDatabaseHelper` class that extends `SQLiteOpenHelper` class. We define the database name and version in the constructor. We also override `onCreate()` method to create a new table with the name `my_table` and three columns - `id`, `name`, and `age`. Finally, we override `onUpgrade()` method to drop the table if it exists and recreate it.

2. SQLite Data Types:

SQLite supports several data types, including INTEGER, TEXT, REAL, BLOB, and NULL. Here's an example of how to create a table with different data types:

```
String sql = "CREATE TABLE my_table ("
        + "id INTEGER PRIMARY KEY AUTOINCREMENT,"
        + "name TEXT,"
        + "age INTEGER,"
        + "height REAL,"
        + "photo BLOB)";
db.execSQL(sql);
```

In the above example, we add four columns to the `my_table` table - `id` with INTEGER data type and PRIMARY KEY constraint, `name` with TEXT data type, `age` with INTEGER data type, `height` with REAL data type, and `photo` with BLOB data type.

3. Cursors and Content Values:

Cursors are used to retrieve data from a SQLite database. Content Values are used to insert, update, and delete data in a SQLite database. Here's an example of how to use Cursors and Content Values:

```
// Retrieve data using a Cursor
String[] columns = {"id", "name", "age"};
Cursor cursor = db.query("my_table", columns, null, null, null, null, null);
while (cursor.moveToNext()) {
    int id = cursor.getInt(cursor.getColumnIndexOrThrow("id"));
    String name = cursor.getString(cursor.getColumnIndexOrThrow("name"));
    int age = cursor.getInt(cursor.getColumnIndexOrThrow("age"));
    // Do something with the retrieved data
}
cursor.close();

// Adding new data
ContentValues values = new ContentValues();
values.put("name", "John");
values.put("age", 30);
db.insert("my_table", null, values);

// Updating data
ContentValues updateValues = new ContentValues();
updateValues.put("age", 35);
String whereClause = "name=?";
String[] whereArgs = {"John"};
db.update("my_table", updateValues, whereClause, whereArgs);

// Deleting data
String deleteWhereClause = "name=?";
String[] deleteWhereArgs = {"John"};
db.delete("my_table", deleteWhereClause, deleteWhereArgs);

```

In the above example, we first retrieve data from the `my_table` table using a Cursor. We define the columns we want to retrieve using the `columns` array. We then use the `query()` method to retrieve the data and iterate through the Cursor to retrieve each row of data. 

we add new data to the `my_table` table using the `insert()` method. We define the values we want to insert using the `ContentValues` object. We then use the `insert()` method to add the data to the table.

We also update data in the `my_table` table using the `update()` method. We define the values we want to update using the `updateValues` object. We also define the `whereClause` and `whereArgs` to specify which rows to update.

Finally, we delete data from the `my_table` table using the `delete()` method. We define the `whereClause` and `whereArgs` to specify which rows to delete.
