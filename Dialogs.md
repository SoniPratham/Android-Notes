## Dialogs

Creating Dialogs:

To create dialogs in Android, follow these steps:

1. Create a new class that extends DialogFragment:

```java
public class ExampleDialogFragment extends DialogFragment {

    @NonNull
    @Override
    public Dialog onCreateDialog(Bundle savedInstanceState) {
        AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
        builder.setTitle("Dialog Title")
               .setMessage("Dialog Message")
               .setPositiveButton("OK", new DialogInterface.OnClickListener() {
                   @Override
                   public void onClick(DialogInterface dialog, int which) {
                       // Handle positive button click
                   }
               })
               .setNegativeButton("Cancel", new DialogInterface.OnClickListener() {
                   @Override
                   public void onClick(DialogInterface dialog, int which) {
                       // Handle negative button click
                   }
               });
        return builder.create();
    }
}
```

2. Show the dialog by calling show() on an instance of the DialogFragment:

```java
ExampleDialogFragment dialog = new ExampleDialogFragment();
dialog.show(getSupportFragmentManager(), "example_dialog");
```

Note: getSupportFragmentManager() is used to get an instance of the FragmentManager in an activity.

These are just a few examples of how to create menus and dialogs in Android. There are many other options and variations available for customizing and extending these UI components.
