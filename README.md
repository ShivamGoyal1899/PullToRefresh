Building Flutter PullToRefresh in just 15 minutes
=================================================

Learn easy implementation of a PullToRefresh gesture in Flutter.
----------------------------------------------------------------

<img src="https://miro.medium.com/max/1400/1*4-cY2F_Yvo9iTOQj51ZegA.png">

Introduction
============

The pull-to-refresh pattern lets a user pull down on a list of data using touch in order to retrieve more data. The "Pull-to-refresh" gesture was first introduced by Loren Brichter in the Tweetie app and in no time it became so popular that countless apps adopted this gesture. Today "pull-to-refresh" feature is a natural part of many popular apps, including Twitter, Gmail, Tweetbot and others.

What you'll build?
------------------

In this tutorial, you'll build a mobile app featuring a PullToRefresh gesture using the Flutter SDK. Your app will:

*   Display a dynamic list with a random number of items
*   Each time you **PullToRefresh** the no of items will change in the list

<img src="https://miro.medium.com/max/4096/1*Wv6VXDMDm-FMSwudouXEEQ.png">


<p align="center">
  That's how our PullToRefresh gonna work
</p>

This tutorial focuses on adding a PullToRefresh gesture to a Flutter app. Non-relevant concepts and code blocks are glossed over and are provided for you to simply copy and paste.

Widget In Focus | [RefreshIndicator](https://api.flutter.dev/flutter/material/RefreshIndicator-class.html)
----------------------------------

* * *

Setting up Flutter on your machine
==================================

The detailed steps to install Flutter on your personal computer & getting started with Flutter is available at the following blog

> [How to install Flutter on Mac & Windows](https://medium.com/enappd/install-flutter-on-windows-and-mac-1fd1dde453ba)

Coding the component
====================

Component Syntax
----------------

The basic format of PullToRefresh gesture looks like the one below:

```dart
const RefreshIndicator({
      Key key,
      @required Widget child,
      double displacement: 40.0,
      @required RefreshCallback onRefresh,
      Color color,
      Color backgroundColor,
      ScrollNotificationPredicate
          notificationPredicate: defaultScrollNotificationPredicate,
      String semanticsLabel,
      String semanticsValue
})
```

Implementation
--------------

The most generic way to implement PullToRefresh is as follows:

```dart
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
```

Importing dart libraries to main.dart file
------------------------------------------

Import **dart:async** & **dart:math** libraries to your main.dart file by adding the following line at the starting of the file:

```dart
import 'dart:async';
import 'dart:math';
```

Putting Code in action
----------------------

Amend your main.dart file as per the following code:

```dart
import 'dart:async';
import 'dart:math';
import 'package:flutter/material.dart';

void main() => runApp(PullToRefresh());

class PullToRefresh extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Pull To Refresh',
      home: HomePage(),
    );
  }
}

class HomePage extends StatefulWidget {
  @override
  _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  var list;
  var random;

  var refreshKey = GlobalKey<RefreshIndicatorState>();

  @override
  void initState() {
    list = List.generate(3, (i) => "Item $i");
    super.initState();
    random = Random();
    refreshList();
  }

  Future<Null> refreshList() async {
    refreshKey.currentState?.show(atTop: false);
    await Future.delayed(Duration(seconds: 2));

    setState(() {
      list = List.generate(random.nextInt(10), (i) => "Item $i");
    });

    return null;
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Pull to refresh"),
      ),
      body: RefreshIndicator(
        key: refreshKey,
        child: ListView.builder(
          itemCount: list?.length,
          itemBuilder: (context, i) => ListTile(
            title: Text(list[i]),
          ),
        ),
        onRefresh: refreshList,
      ),
    );
  }
}
```

Building & running the application
----------------------------------

*   Connect your Emulator or physical Android device to test the application.
*   Click on Build & Run.
*   And Boooom :boom:, your app is ready.  
    The final build would look like the below illustration.

<img src="https://miro.medium.com/max/1200/1*Xdgqe3NAYSk44UMl2Qswlw.gif"/>

<p align="center">
The final output of the implementation
</p>

* * *
