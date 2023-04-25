## Firebase Database



Here are the steps to create a simple login app with Firebase connection in Android:

1. Create a new Android Studio project and add the Firebase SDK to your project. Follow the instructions from Firebase documentation on how to add Firebase to your Android project.

2. Add the Firebase Authentication dependency to your project by adding the following line to the app-level build.gradle file:

   ```
   implementation 'com.google.firebase:firebase-auth:19.3.0'
   ```

3. Create a new activity for the login screen and add the UI elements such as EditText for email and password, and Button for login.

4. In your activity's Java code, create a FirebaseAuth instance and use it to handle the login process. You can use the signInWithEmailAndPassword method to sign in with the email and password entered by the user.

   ```
   FirebaseAuth mAuth;
   mAuth = FirebaseAuth.getInstance();

   // Login button click listener
   loginBtn.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           String email = emailEditText.getText().toString().trim();
           String password = passwordEditText.getText().toString().trim();

           mAuth.signInWithEmailAndPassword(email, password)
                   .addOnCompleteListener(new OnCompleteListener<AuthResult>() {
                       @Override
                       public void onComplete(@NonNull Task<AuthResult> task) {
                           if (task.isSuccessful()) {
                               // Login successful
                               // Move to the next screen
                           } else {
                               // Login failed
                               // Show an error message
                           }
                       }
                   });
       }
   });
   ```

5. Handle the login process result in the onComplete method of the signInWithEmailAndPassword method. If the login is successful, you can move the user to the next screen. If the login fails, you can show an error message to the user.

That's it! You have now created a simple login app with Firebase connection in Android.
