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