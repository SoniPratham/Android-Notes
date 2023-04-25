## Notification in Android

Notifications are a crucial part of the Android system as they provide timely and relevant information to users. Notifications can be used to inform users about events, updates, reminders, and more. Android provides a powerful Notification API that developers can use to create and display notifications in their apps.

Here are the steps involved in creating and displaying notifications in Android:

1. Notification Channel:

The first step is to create a Notification Channel. A Notification Channel is a way to group notifications based on their importance and category. For example, you might have a channel for notifications related to emails and another channel for notifications related to social media. To create a Notification Channel, you need to create an instance of NotificationChannel class and provide a name, description, and importance level. You can then register the channel with the Notification Manager using the `createNotificationChannel()` method.

2. Notification Builder:

The next step is to create a Notification Builder. A Notification Builder is used to create a notification with various properties such as title, message, icon, etc. You can create a new Notification Builder using the NotificationCompat.Builder class. You can set various properties of the notification using the methods provided by the NotificationCompat.Builder class.

3. Notification Action:

You can also add actions to the notification. An action is a button that appears below the notification and allows the user to perform a specific action. To add an action, you need to create an instance of NotificationCompat.Action class and provide a title and icon for the action. You can then add the action to the notification using the `addAction()` method.

4. Notification Manager:

Finally, you need to use the Notification Manager to display the notification. You can get an instance of the Notification Manager using the `getSystemService()` method. You can then call the `notify()` method to display the notification. The `notify()` method takes two parameters: the ID of the notification and the Notification object.

Here's an example of how to create and display a notification in Android:

```
// Create a Notification Channel
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
    NotificationChannel channel = new NotificationChannel("channel_id", "Channel Name", NotificationManager.IMPORTANCE_HIGH);
    NotificationManager notificationManager = getSystemService(NotificationManager.class);
    notificationManager.createNotificationChannel(channel);
}

// Create a Notification Builder
NotificationCompat.Builder builder = new NotificationCompat.Builder(this, "channel_id")
    .setSmallIcon(R.drawable.notification_icon)
    .setContentTitle("Notification Title")
    .setContentText("Notification Message")
    .setPriority(NotificationCompat.PRIORITY_HIGH)
    .addAction(R.drawable.action_icon, "Action Title", null);

// Display the Notification
NotificationManagerCompat notificationManager = NotificationManagerCompat.from(this);
notificationManager.notify(1, builder.build());
```

In the above example, we first create a Notification Channel using the `NotificationChannel` class and register it with the Notification Manager. We then create a Notification Builder using the `NotificationCompat.Builder` class and set various properties of the notification. We also add an action to the notification using the `addAction()` method.

Finally, we display the notification using the Notification Manager. We get an instance of the Notification Manager using the `NotificationManagerCompat.from()` method and call the `notify()` method to display the notification. The first parameter of the `notify()` method is the ID of the notification, and the second parameter is the Notification object created by the Notification Builder.
