## Binding Data with the AdapterView Class- ListView, Spinner

Adapters are used to bind data to AdapterView classes in Android. Here are the examples of how to bind data to ListView and Spinner using ArrayAdapter:

1. ListView:

```
// Get the reference of ListView
ListView listView = findViewById(R.id.listView);

// Create a list of data
List<String> dataList = new ArrayList<>();
dataList.add("Item 1");
dataList.add("Item 2");
dataList.add("Item 3");

// Create an ArrayAdapter to bind data to ListView
ArrayAdapter<String> adapter = new ArrayAdapter<>(this,
        android.R.layout.simple_list_item_1, dataList);

// Set the adapter to ListView
listView.setAdapter(adapter);
```

In the above example, we first get the reference of ListView using `findViewById()`. We then create a list of data and an `ArrayAdapter` to bind the data to ListView. Finally, we set the adapter to ListView using `setAdapter()` method.

2. Spinner:

```
// Get the reference of Spinner
Spinner spinner = findViewById(R.id.spinner);

// Create a list of data
List<String> dataList = new ArrayList<>();
dataList.add("Item 1");
dataList.add("Item 2");
dataList.add("Item 3");

// Create an ArrayAdapter to bind data to Spinner
ArrayAdapter<String> adapter = new ArrayAdapter<>(this,
        android.R.layout.simple_spinner_item, dataList);

// Set the dropdown layout style for the adapter
adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);

// Set the adapter to Spinner
spinner.setAdapter(adapter);
```

In the above example, we first get the reference of Spinner using `findViewById()`. We then create a list of data and an `ArrayAdapter` to bind the data to Spinner. We also set the dropdown layout style for the adapter using `setDropDownViewResource()` method. Finally, we set the adapter to Spinner using `setAdapter()` method.

I hope this helps!
