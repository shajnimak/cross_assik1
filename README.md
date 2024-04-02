# flutter_app

A new Flutter project.

##Downloaded all specified packages for creating an application for Assignment 1:
  ```dependencies:
  flutter:
    sdk: flutter
  wave: ^0.2.2
  flutter_villains: ^2.0.0```
```import 'package:wave/config.dart';
import 'package:wave/wave.dart';
import 'package:flutter_villains/villain.dart';```


## Fast check main code
```import 'package:flutter/material.dart';
import 'package:wave/config.dart';
import 'package:wave/wave.dart';
import 'package:flutter_villains/villain.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Shadyman\'s Flutter App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Package Demo'),
      ),
      body: Stack(
        children: [
          WaveWidget(
            config: CustomConfig(
              gradients: [
                [Colors.blue, Colors.blue.shade200],
                [Colors.blue.shade200, Colors.blue.shade100],
              ],
              durations: [19440, 10800],
              heightPercentages: [0.20, 0.25],
              blur: MaskFilter.blur(BlurStyle.solid, 10),
              gradientBegin: Alignment.bottomLeft,
              gradientEnd: Alignment.topRight,
            ),
            waveAmplitude: 0,
            size: Size(double.infinity, double.infinity),
          ),
          Center(
            child: Villain(
              villainAnimation: VillainAnimation.fromTop(
                from: Duration(milliseconds: 500),
                to: Duration(milliseconds: 1000),
              ),
              child: Container(
                width: 200,
                height: 200,
                color: Colors.white,
                child: Center(
                  child: Text(
                    'SUIIIII',
                    style: TextStyle(fontSize: 24),
                  ),
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
}
```
