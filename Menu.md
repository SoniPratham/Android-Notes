## Menus

In Android, menus and dialogs are common UI components that are used to provide users with additional options and information. Here's a brief overview of how to create menus and dialogs in an Android app:

Creating Menus:

To create menus in Android, follow these steps:

1. Create a new XML file in the res/menu directory with the menu items:

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/menu_item"
        android:title="Menu Item" />
</menu>
```

2. Override onCreateOptionsMenu() in your activity or fragment to inflate the menu:

```java
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.menu_file, menu);
    return true;
}
```

3. Override onOptionsItemSelected() to handle menu item selections:

```java
@Override
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();

    if (id == R.id.menu_item) {
        // Handle menu item click
        return true;
    }

    return super.onOptionsItemSelected(item);
}
```
