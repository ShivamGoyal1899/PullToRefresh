
# Building Flutter PullToRefresh in just 15 minutes

## Introduction

The pull-to-refresh pattern lets a user pull down on a list of data using touch in order to retrieve more data. The “Pull-to-refresh” gesture was first introduced by Loren Brichter in the Tweetie app and in no time it became so popular that countless apps adopted this gesture. Today “pull-to-refresh” feature is a natural part of many popular apps, including Twitter, Gmail, Tweetbot and others.

### What you’ll build?

In this tutorial, you’ll build a mobile app featuring a PullToRefresh gesture using the Flutter SDK. Your app will:

* Display a dynamic list with a random number of items

* Each time you **PullToRefresh** the no of items will change in the list

![That’s how our PullToRefresh gonna work](https://cdn-images-1.medium.com/max/4096/1*Wv6VXDMDm-FMSwudouXEEQ.png)*That’s how our PullToRefresh gonna work*

This tutorial focuses on adding a PullToRefresh gesture to a Flutter app. Non-relevant concepts and code blocks are glossed over and are provided for you to simply copy and paste.

### Github Repository | @ShivamGoyal1899
[**ShivamGoyal1899/DateTimePicker**
*An app featuring DateTimePicker using the Flutter SDK — ShivamGoyal1899/DateTimePicker*github.com](https://github.com/ShivamGoyal1899/DateTimePicker)

### Widget In Focus | RefreshIndicator
[**RefreshIndicator class - material library - Dart API**
*API docs for the RefreshIndicator class from the material library, for the Dart programming language.*api.flutter.dev](https://api.flutter.dev/flutter/material/RefreshIndicator-class.html)

## Setting up Flutter on your machine

The detailed steps to install Flutter on your personal computer & getting started with Flutter is available at the following blog
[**How to install Flutter and create a simple Flutter app **
*Learn what is Flutter and how to set it up on Windows and Mac systems and get started with Flutter apps*medium.com](https://medium.com/enappd/install-flutter-on-windows-and-mac-1fd1dde453ba)

## Coding the component

### Component Syntax

The basic format of PullToRefresh gesture looks like the one below:

    const **RefreshIndicator**({
          **Key** key,
          @required Widget child,
          double **displacement**: 40.0,
          @required **RefreshCallback** onRefresh,
          **Color** color,
          **Color** backgroundColor,
          **ScrollNotificationPredicate**
              notificationPredicate: defaultScrollNotificationPredicate,
          **String** semanticsLabel,
          **String** semanticsValue
    })

### Implementation

The most generic way to implement PullToRefresh is as follows:

    const RefreshIndicator({
      Key key,
      @required this.child,
      this.displacement = 40.0,
      @required this.onRefresh,
      this.color,
      this.backgroundColor,
      this.notificationPredicate = defaultScrollNotificationPredicate,
      this.semanticsLabel,
      this.semanticsValue,
    }) : assert(child != null),
         assert(onRefresh != null),
         assert(notificationPredicate != null),
         super(key: key);

### Importing dart libraries to main.dart file

Import **dart:async** & **dart:math **libraries to your main.dart file by adding the following line at the starting of the file:

    import 'dart:async';
    import 'dart:math';

### Putting Code in action

Amend your main.dart file as per the following code:

<iframe src="https://medium.com/media/53f4b467d40b737dc8bf4b5bc3db5103" frameborder=0></iframe>

### Building & running the application

* Connect your Emulator or physical Android device to test the application.

* Click on Build & Run.

* And Boooom, your app is ready.
The final build would look like the below illustration.

![The final output of the implementation](https://cdn-images-1.medium.com/max/2000/1*Xdgqe3NAYSk44UMl2Qswlw.gif)*The final output of the implementation*

## Enappd Store | Premium App Starters
[Enappd | Ionic, React Native, Firebase themes, templates and starters**
*Get the full source code for Ionic, React Native, Firebase mobile app templates and starters. Use free templates and…*store.enappd.com](https://store.enappd.com/)

## More resources for Flutter

* [Getting Started with Flutter](https://medium.com/enappd/install-flutter-on-windows-and-mac-1fd1dde453ba)

* [Implementing Facebook Auth in Flutter](https://medium.com/enappd/flutter-tutorial-for-native-app-building-and-facebook-authentication-978f0ee44976)

* [Building a Flutter DateTime Picker in just 15 minutes](https://medium.com/enappd/building-a-flutter-datetime-picker-in-just-15-minutes-6a4b13d6a6d1)

* [Flutter Documentation](https://flutter.dev/docs)

* [Flutter Community](https://flutter.dev/community)

* [Flutter YouTube Channel](https://www.youtube.com/flutterdev)

* My GitHub Profile [@ShivamGoyal1899](https://github.com/ShivamGoyal1899)
