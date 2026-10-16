# Build a Simple Counter App

## Activity Objectives
By the end of this activity, you should be able to:
1. Create a basic Android application using Kotlin and Jetpack Compose.
2. Design a simple user interface using Compose components such as Column, Row, Text, and Button.
3. Use state to store and update a value within an application.
4. Implement button-click events.
5. Explain how changes to state are reflected in the user interface.
6. Run and test the application using an Android emulator or physical device.
7. Reflect on how user interactions and state work together in an Android application.

## What are we doing?
In this activity, you will create a Simple Counter app from scratch using Android Studio.

The app should display a number, starting at 0, with two buttons. One button increases the number and the other decreases it. As you press the buttons, the number displayed on the screen should change immediately.

## 1. Create your project

Open Android Studio and create a new project:
1. Select New Project
1. Select Empty Activity (the Jetpack Compose template).
1. Set the app name to Simple Counter.
1. Use this exact package name: `com.prog7313.simplecounter`.
1. Select Kotlin and finish creating the project.
1. Allow Gradle to sync, and open `MainActivity.kt`.

> Note: Gradle sync will take a while the first time you run your app. This is normal behaviour.

## 2. Design the user interface

Inside your Compose screen, create the following layout:
- A heading: Simple Counter.
- A large number showing the current count.
- Two buttons next to each other: − and +.

Use a `Column` to arrange the content vertically and a `Row` for the two buttons. You can use `Text`, `Button`, and `Spacer` to put the screen together.

## 3. Make the buttons work

As you build the app, you will need several elements.

Add a variable that Compose can observe. Add this inside your `@Composable` counter screen:

```kotlin
var count by remember { mutableIntStateOf(0) }
```

You should display the value of `count` using a Compose element:

```kotlin
Text(text = "$count")
```

You will need buttons with actions behind them:
```kotlin
Button(onClick = { count-- }) { Text("−") }
Button(onClick = { count++ }) { Text("+") }
```

You'll need imports for Compose `remember`, `mutableIntStateOf`, `getValue` and `setValue`. Android Studio will guide you through these.

## 4. Test your app

Make sure that your app works in the following manner (for now, manual testing is fine):
- Displays the current count.
- Increases it by one.
- Decreases it by one.

Additional Challenge (if you finish early):
- Add a Reset button that sets the counter back to "0".
- Prevent the counter from going into negative.

> What is considered complete? Your app must show a number and both buttons must work. You should also be able to explain, in your own words, how pressing a button updates the screen.

## 5. Save your work
Commit your work to your own GitHub repository 

## 6. Let's discuss and reflect
We will discuss with audio or you are welcome to post in the chat:
1. [Reflect] How different is Android Studio from Visual Studio? What is similar and what is different?
1. [Reflect] Which resources did you consult when completing this activity? Make sure to bookmark sites that you found helpful
1. [Code discussion] What happens to the displayed value when `count` changes?
1. [Code discussion] Why have we used `remember` and `mutableIntStateOf` rather than a normal integer variable?
1. [Code discussion] What did you find easiest, and what would you like to revise before the next session?