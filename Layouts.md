## Working with View Groups- LinearLayout, ScrollView, Table, Frame, Table with ActionBar

ViewGroups are containers for Views and other ViewGroups. Here are some commonly used ViewGroups and their brief explanations with examples:

1. LinearLayout: A LinearLayout is a view group that arranges child views in either a horizontal or vertical direction, based on the orientation set on the LinearLayout.

Example:

```
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Name:" />

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter your name" />

</LinearLayout>
```

2. ScrollView: A ScrollView is a view group that provides a scrolling view of its contents. It is used when the contents of the layout cannot fit on the screen.

Example:

```
<ScrollView
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <!-- Child views -->

    </LinearLayout>

</ScrollView>
```

3. TableLayout: A TableLayout is a view group that arranges its child views in a table structure. It is used when you want to display data in a tabular format.

Example:

```
<TableLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <TableRow>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Name" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Age" />

    </TableRow>

    <TableRow>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="John" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="25" />

    </TableRow>

</TableLayout>
```

4. FrameLayout: A FrameLayout is a view group that displays one child view at a time. It is often used to display fragments in an activity.

Example:

```
<FrameLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- Fragment or child view -->

</FrameLayout>
```

5. TableLayout with ActionBar: A TableLayout with ActionBar is similar to a regular TableLayout, but it also includes an ActionBar at the top of the screen.

Example:

```
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <android.support.v7.widget.Toolbar
        android:id="@+id/toolbar"
        android:layout_width="match_parent"
        android:layout_height="?attr/actionBarSize"
        android:background="?attr/colorPrimary"
        android:title="My Title"
        android:titleTextColor="@android:color/white" />

    <TableLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!-- Child views -->

    </TableLayout>

</LinearLayout>
```

I hope this helps!
