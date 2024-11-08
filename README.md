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