# ASSIGNMENT 7

## Explain what are stateless widgets and stateful widgets, and explain the difference between them.

A Stateless Widget is a widget that does not hold or depend on any state that can change. Once created, it cannot change its appearance or behavior based on user interaction or other factors. Stateless widgets are immutable, meaning that their properties cannot change after being initialized. They are typically used for displaying static content.

Example: Common widgets like Text, Icon, and Image are stateless.


A Stateful Widget is a widget that can rebuild itself based on changes in its internal state. This widget is mutable, meaning it can update and react to user interactions, data changes, animations, timers, or any other factor that would alter its appearance or behavior.

Example: Widgets like Checkbox, Slider, and TextField are stateful because they can change based on user interaction.


## Mention the widgets that you have used for this project and its uses.

Scaffold: Provides the main structure for the screen, including areas for the AppBar and body. In this project, it structures the home page layout with an app bar at the top and the main content in the body.

GridView.count: Arranges child widgets in a grid format. Here, it’s used to display a 3-column grid of action items (e.g., "View Mood," "Add Mood," "Logout"), making them organized and visually appealing.

InkWell: A widget that adds tap functionality, giving a visual effect when tapped. In this project, InkWell wraps each ItemCard, allowing a SnackBar message to show when a card is tapped.

## What is the use-case for setState()? Explain the variable that can be affected by setState().

The setState() method is used in stateful widgets to update the UI in response to changes in a widget’s state. When called, setState() triggers a rebuild of the widget, ensuring that any visual changes or data updates are reflected in the user interface. Variables affected by setState() are typically state variables defined within the State class.

## Explain the difference between const and final keyword.

In Dart, both const and final are used to create variables that cannot be reassigned, but they differ in when their values are determined. The final keyword allows variables to be assigned only once but can hold values set at runtime, making it suitable for variables that get initialized when the program runs (e.g., final currentTime = DateTime.now()). On the other hand, const is used for compile-time constants, meaning the value must be known and fixed during compilation, like const pi = 3.14159. In summary, final is for values that should not change once set, even if set at runtime, while const is for values that are unchanging and known in advance.

## Explain how you implemented the checklist above step-by-step.

First I created a new folder virtualshop-mobile and a github repository. After that is done I create a new flutter app and also change the flutter config to enable web support. After that is done I created the menu.dart file inside the lib folder. After that is done I copy the main.dart and menu.dart tutorial code, then I modify the menu.dart so it followed the requirements that the assignment needs.



# ASSIGNMENT 8


## What is the purpose of const in Flutter? Explain the advantages of using const in Flutter code. When should we use const, and when should it not be used?

In Flutter, `const` is used to create compile-time constants. It is particularly useful for optimizing performance in widget trees by making widgets immutable. When you declare a widget or variable as `const`, Flutter knows that it won't change, allowing the widget to be built only once and reused whenever needed without being rebuilt.

### Advantages of using `const` in Flutter
- **Improves Performance**: Constant widgets don’t need to be rebuilt, which reduces unnecessary widget rebuilds.
- **Optimizes Memory Usage**: Since `const` widgets are reused, memory usage is minimized because they are stored once and referenced multiple times.
- **Code Clarity and Safety**: Declaring values as `const` signals that these values won’t change, helping to avoid bugs related to unintended changes.

### When to Use `const`
- Use `const` for widgets that won’t change after they are created (e.g., `Text` with static content, decorations, padding).
- Apply `const` when initializing objects that take only constant values, like `TextStyle` and `EdgeInsets`.

### When Not to Use `const`
- Don’t use `const` when the widget or value might change based on user interaction or app state, as this would require a rebuild.
- Avoid `const` in widgets that rely on dynamic data or variables that might change over time.



## Explain and compare the usage of Column and Row in Flutter. Provide example implementations of each layout widget!

In Flutter, `Column` and `Row` are layout widgets used to arrange their child widgets vertically (`Column`) and horizontally (`Row`). Both widgets allow you to align, space, and organize multiple children flexibly.

### Column
- Arranges widgets vertically.
- Ideal for layouts where elements need to be stacked on top of each other.

#### Example:

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```


## List the input elements you used on the form page in this assignment. Are there other Flutter input elements you didn’t use in this assignment? Explain!

### Input Elements Used
- **TextFormField**: Used for single-line text input, such as name and description fields.
- **ElevatedButton**: A clickable button used for form submission or actions.

### Other Flutter Input Elements Not Used
- **Checkbox**: Used for multi-select options, ideal for things like "terms and conditions."
- **Radio**: For single-choice selections among multiple options, like payment methods.
- **Switch**: A toggle for on/off actions, useful for settings.
- **Slider**: Used to select a numeric value within a range.
- **DatePicker**: A calendar-based picker for date selection.
- **DropdownButton**: Allows users to pick an option from a list, useful for lists like country selection.

These elements provide a wide variety of input options for form-based Flutter applications.



## How do you set the theme within a Flutter application to ensure consistency? Did you implement a theme in your application?

In Flutter, themes help to maintain consistent styling throughout the application, including colors, fonts, and widget appearances. Themes are defined in the `MaterialApp` widget, allowing you to control the visual styling of your entire app from a single place. This approach ensures a unified look and feel across screens, reducing the need for inline styling.


## How to Set a Theme in Flutter

To set a theme, define a `ThemeData` object within the `MaterialApp` widget in your `main.dart` file. The `ThemeData` object contains properties for configuring primary colors, text styles, button appearances, and more.

### Example of Theme Setup

```dart
MaterialApp(
  theme: ThemeData(
    primaryColor: Colors.blue,
    colorScheme: ColorScheme.fromSwatch(
      primarySwatch: Colors.blue,
    ).copyWith(
      secondary: Colors.amber,
    ),
    textTheme: TextTheme(
      bodyText2: TextStyle(color: Colors.black87),
      headline6: TextStyle(fontWeight: FontWeight.bold),
    ),
    buttonTheme: ButtonThemeData(
      buttonColor: Colors.blue, // Default button color
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(8.0),
      ),
    ),
  ),
  home: MyHomePage(),
);

```

In my application I didn't implement a theme

## How do you manage navigation in a multi-page Flutter application?

In a multi-page Flutter application, navigation is managed using the `Navigator` widget. The `Navigator` widget maintains a stack-based structure, allowing pages (also called routes) to be pushed onto or popped off the stack. This README explains key methods for navigation, as well as how to use named routes for more efficient management.


## Key Methods for Navigation

Flutter provides several methods to navigate between screens:

### 1. `Navigator.push`
This method pushes a new route onto the stack, creating a transition to a new page on top of the current one.

```dart
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => NewPage()),
);

```

# ASSIGNMENT 9

## 1. Why Do We Need to Create a Model to Retrieve or Send JSON Data?

1. **Structured Data**: Models ensure that the JSON data exchanged between systems adheres to a specific structure, minimizing errors related to missing fields or incorrect data types.
2. **Improved Usability**: By using models, developers can interact with data through well-defined attributes instead of handling raw JSON strings, making the code cleaner, more understandable, and easier to maintain.
3. **Validation and Consistency**: Models enable the enforcement of validation rules, making it easier to identify and address data inconsistencies early in the process.

**Risks of Not Using a Model**:  
While it's possible to handle JSON data without models, this approach often results in increased complexity and a higher likelihood of runtime errors. Manually parsing JSON can lead to bugs due to unhandled null values or type mismatches, ultimately reducing the reliability and maintainability of the code.

## 2. The Function of the `http` Library

1. **Fetching Data (GET Requests)**: Allows the app to retrieve data from a server.
2. **Sending Data (POST Requests)**: Enables the app to send data to the server for tasks like form submissions or database updates.
3. **Updating Data (PUT/PATCH Requests)**: Facilitates updating existing resources on the server.
4. **Deleting Data (DELETE Requests)**: Handles the removal of resources on the server.

This library simplifies the process of making HTTP requests by managing headers, status codes, and JSON encoding/decoding, streamlining server communication and ensuring efficient data transmission.


## 3. The Function of `CookieRequest` and Its Importance

1. **Session Management**: `CookieRequest` maintains cookies across multiple HTTP requests, ensuring that session data persists throughout the user's interaction with the app.
2. **Authentication Support**: It enables seamless user authentication by saving and sending session cookies, ensuring users remain logged in without requiring repeated credential entry.
3. **Security Enhancement**: Proper cookie handling helps secure sensitive data by allowing access to resources only for authenticated users.

### Why `CookieRequest` is Important:
- **State Consistency**: Ensures all parts of the app share the same session state, avoiding discrepancies across different components.
- **Simplified Session Handling**: Eliminates the need for manual management of cookies, reducing the complexity of managing user sessions securely.


### 4. Why Share `CookieRequest` Across Components?

1. **Session Consistency**: A shared `CookieRequest` ensures that all parts of the app operate with the same session state, maintaining a unified and seamless user experience.
2. **Efficient Session Management**: Using a single instance avoids the overhead of managing multiple instances and prevents issues like session desynchronization or conflicts.
3. **Simplified Development**: Centralizing session handling reduces complexity, making the codebase easier to maintain and debug.
4. **Secure Data Handling**: With a shared `CookieRequest`, sensitive session data is stored and transmitted consistently across requests, enhancing security and reliability.


## 5. Mechanism of Data Transmission in Flutter
Data transmission in Flutter typically involves sending and receiving data between the app and a server. Here’s the step-by-step process:

1. **User Interaction**:  
   The user interacts with the app's UI, such as filling out a form, clicking a button, or selecting an option.
2. **Data Collection**:  
   The app gathers user input and structures it into a suitable format, usually as a JSON object, for transmission.
3. **Request Formation**:  
   Using libraries like `http` or utilities such as `CookieRequest`, the app constructs an HTTP request (e.g., GET, POST, PUT, or DELETE) and includes necessary data, headers, and authentication tokens (if required).
4. **Server Communication**:  
   The app sends the request to the server endpoint. The server processes the request, performs necessary operations (e.g., database queries), and prepares a response.
5. **Response Handling**:  
   The server returns a response to the app, often in JSON format, containing the requested data, a success message, or error details.
6. **Data Parsing**:  
   The app parses the server response, converting JSON data into usable objects or models for further processing.
7. **UI Update**:  
   Based on the parsed data, the app updates the UI, displaying new information, error messages, or confirmation notifications to the user.
This mechanism ensures smooth data flow between the Flutter app and the server, enabling dynamic and interactive user experiences.



## 6. Authentication Mechanism in Flutter and Django

### **Login Flow**:
1. **User Input**:  
   The user enters their credentials (username/email and password) into the Flutter app.

2. **Send POST Request**:  
   Flutter sends the login data as a POST request using libraries like `http` or `CookieRequest` to Django's authentication endpoint.

3. **Django Validates Credentials**:  
   - Django checks the submitted credentials against the database.
   - If valid, Django creates a session, generates a session cookie, and includes it in the response.

4. **Store Session Cookie**:  
   - The session cookie is stored by `CookieRequest` in Flutter to maintain the user’s logged-in state for subsequent requests.

5. **UI Update**:  
   Flutter updates the app's UI to reflect the logged-in state (e.g., navigating to a dashboard).


### **Registration Flow**:
1. **User Input**:  
   The user fills out a registration form in the Flutter app with details such as username, email, and password.

2. **Send POST Request**:  
   Flutter sends this data to Django’s registration endpoint via a POST request.

3. **Django Creates User**:  
   - Django validates the input data (e.g., unique username, strong password).
   - If valid, it creates a new user in the database and returns a success response.

4. **UI Update**:  
   Flutter displays a confirmation message or navigates to the login page.


### **Logout Flow**:
1. **Logout Trigger**:  
   The user clicks a logout button in the Flutter app.

2. **Send Logout Request**:  
   Flutter sends a POST or GET request (depending on the implementation) to Django’s logout endpoint using `CookieRequest`.

3. **Django Ends Session**:  
   - Django clears the session data and invalidates the session cookie.
   - It responds with a success message.

4. **Clear Session Data**:  
   `CookieRequest` clears the stored session cookie in Flutter.

5. **UI Update**:  
   Flutter updates the UI to reflect the logged-out state (e.g., navigating back to the login screen).


## 7. Implementation Steps


## Step 1: Backend Setup (Django)

### 1.1 Create Django Views for Authentication

#### `views.py`:
```python
from django.views.decorators.csrf import csrf_exempt
from django.contrib.auth import authenticate, login as auth_login, logout as auth_logout
from django.http import JsonResponse
import json
from django.contrib.auth.models import User

@csrf_exempt
def login(request):
    username = request.POST['username']
    password = request.POST['password']
    user = authenticate(username=username, password=password)
    if user is not None:
        if user.is_active:
            auth_login(request, user)
            return JsonResponse({
                "username": user.username,
                "status": True,
                "message": "Login successful!"
            }, status=200)
        else:
            return JsonResponse({
                "status": False,
                "message": "Login failed, account disabled."
            }, status=401)
    else:
        return JsonResponse({
            "status": False,
            "message": "Login failed, check username or password again."
        }, status=401)

@csrf_exempt
def register(request):
    if request.method == 'POST':
        data = json.loads(request.body)
        username = data['username']
        password1 = data['password1']
        password2 = data['password2']

        if password1 != password2:
            return JsonResponse({
                "status": False,
                "message": "Passwords do not match."
            }, status=400)

        if User.objects.filter(username=username).exists():
            return JsonResponse({
                "status": False,
                "message": "Username already exists."
            }, status=400)

        user = User.objects.create_user(username=username, password=password1)
        user.save()

        return JsonResponse({
            "username": user.username,
            "status": 'success',
            "message": "User created successfully!"
        }, status=200)

    else:
        return JsonResponse({
            "status": False,
            "message": "Invalid request method."
        }, status=400)

@csrf_exempt
def logout(request):
    username = request.user.username
    try:
        auth_logout(request)
        return JsonResponse({
            "username": username,
            "status": True,
            "message": "Logged out successfully!"
        }, status=200)
    except:
        return JsonResponse({
            "status": False,
            "message": "Logout failed."
        }, status=401)
```

---

## Step 2: Flutter App Setup

### 2.1 Login Screen

#### `login.dart`:
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:virtualshop/screens/menu.dart';
import 'package:virtualshop/screens/register.dart';
import '../utils/cookie_request.dart';

class LoginPage extends StatefulWidget {
  const LoginPage({super.key});

  @override
  State<LoginPage> createState() => _LoginPageState();
}

class _LoginPageState extends State<LoginPage> {
  final TextEditingController _usernameController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    final request = context.watch<CookieRequest>();

    return Scaffold(
      appBar: AppBar(title: const Text('Login')),
      body: Center(
        child: SingleChildScrollView(
          padding: const EdgeInsets.all(16.0),
          child: Card(
            elevation: 8,
            shape: RoundedRectangleBorder(
              borderRadius: BorderRadius.circular(12.0),
            ),
            child: Padding(
              padding: const EdgeInsets.all(20.0),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  const Text(
                    'Login',
                    style: TextStyle(fontSize: 24.0, fontWeight: FontWeight.bold),
                  ),
                  const SizedBox(height: 30.0),
                  TextField(
                    controller: _usernameController,
                    decoration: const InputDecoration(
                      labelText: 'Username',
                      hintText: 'Enter your username',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                    ),
                  ),
                  const SizedBox(height: 12.0),
                  TextField(
                    controller: _passwordController,
                    decoration: const InputDecoration(
                      labelText: 'Password',
                      hintText: 'Enter your password',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                    ),
                    obscureText: true,
                  ),
                  const SizedBox(height: 24.0),
                  ElevatedButton(
                    onPressed: () async {
                      String username = _usernameController.text;
                      String password = _passwordController.text;
                      final response = await request.login(
                          "http://127.0.0.1:8000/auth/login/", {
                        'username': username,
                        'password': password,
                      });

                      if (request.loggedIn) {
                        String message = response['message'];
                        String uname = response['username'];
                        if (context.mounted) {
                          Navigator.pushReplacement(
                            context,
                            MaterialPageRoute(builder: (context) => MyHomePage()),
                          );
                          ScaffoldMessenger.of(context)
                            ..hideCurrentSnackBar()
                            ..showSnackBar(SnackBar(
                              content: Text("$message Welcome, $uname."),
                            ));
                        }
                      } else {
                        if (context.mounted) {
                          showDialog(
                            context: context,
                            builder: (context) => AlertDialog(
                              title: const Text('Login Failed'),
                              content: Text(response['message']),
                              actions: [
                                TextButton(
                                  child: const Text('OK'),
                                  onPressed: () {
                                    Navigator.pop(context);
                                  },
                                ),
                              ],
                            ),
                          );
                        }
                      }
                    },
                    child: const Text('Login'),
                  ),
                  const SizedBox(height: 36.0),
                  GestureDetector(
                    onTap: () {
                      Navigator.push(
                        context,
                        MaterialPageRoute(builder: (context) => const RegisterPage()),
                      );
                    },
                    child: Text(
                      'Don\'t have an account? Register',
                      style: TextStyle(
                        color: Theme.of(context).colorScheme.primary,
                        fontSize: 16.0,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

---

### 2.2 Register Screen

#### `register.dart`:
Similar to `login.dart`, define the `RegisterPage` class with a form to register a new user, using the `register` endpoint.

---

### 2.3 Product Model for Flutter

#### `product_entry.dart`:
```dart


import 'dart:convert';

List<ProductEntry> productEntryFromJson(String str) =>
    List<ProductEntry>.from(json.decode(str).map((x) => ProductEntry.fromJson(x)));

class ProductEntry {
  String model;
  String pk;
  Fields fields;

  ProductEntry({required this.model, required this.pk, required this.fields});

  factory ProductEntry.fromJson(Map<String, dynamic> json) => ProductEntry(
        model: json["model"],
        pk: json["pk"],
        fields: Fields.fromJson(json["fields"]),
      );
}

class Fields {
  int user;
  String name;
  int price;
  String description;

  Fields({required this.user, required this.name, required this.price, required this.description});

  factory Fields.fromJson(Map<String, dynamic> json) => Fields(
        user: json["user"],
        name: json["name"],
        price: json["price"],
        description: json["description"],
      );
}
```


