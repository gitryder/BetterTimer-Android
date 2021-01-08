# BetterTimer [![](https://jitpack.io/v/gitryder/BetterTimer-Android.svg)](https://jitpack.io/#gitryder/BetterTimer-Android) 

BetterTimer is the fastest way to implement a timer in Android. It solves some of CountDownTimer's problems<sup> [1](#%EF%B8%8F-citations) </sup> and provides a robust API for interfacing<sup> [2](#%EF%B8%8F-citations) </sup> with the timer

<p>
  <img src="static/better_timer_logo.svg" width="500"/>
</p>

![](https://github.com/gitryder/better-timer/blob/main/static/ctd_vs_bt.gif)
 
 👨‍🔧 Installation
 ==================
Add this to your app's project-level `build.gradle` file:
 
```gradle
repositories {
  maven { url 'https://jitpack.io' }
}
```
And this to your app's module-level `build.gradle` file:

```gradle
dependencies {
  implementation 'com.github.gitryder:better-timer:v0.2-alpha'
}
```
🚀 Usage
========
1. Have your `Activity` implement `BetterTimer.OnTimerTickListener`
```diff
- class MainActivity : AppCompatActivity() { ... }
+ class MainActivity : AppCompatActivity(), BetterTimer.OnTimerTickListener { ... }
```
2. Create an instance of `BetterTimer`
  - Pass the time (in minutes)
  - Pass the activity context (this) to receive callbacks
```kotlin
val timer = BetterTimer(25, this)
```
3. Call the timer methods as you please
```kotlin
timerStartButton.setOnClickListener { 
    timer.start()  
    // Update UI Logic
}
```

```kotlin
timerPauseButton.setOnClickListener { 
    timer.pause()
    // Update UI Logic
}
```

```kotlin
timerResetButton.setOnClickListener { 
    timer.reset()         
    // Update UI Logic
}
```
4. Update the view that displays the time, in the `onTimerTick()` callback
```kotlin
override fun onTimerTick(timeUntilFinished: String) {
    timerDisplayTextview.text = timeUntilFinished
}
```
🌄 Contribute to this project
=============================
1. Fork this repo (git clone https://github.com/gitryder/better-timer.git)
2. Create a feature branch (git checkout -b a-new-feature)
3. Commit your work (git commit -am 'Add new feature')
4. Push to your branch (git push origin a-new-feature)
5. Create a shiny new Pull Request
6. Pat yourself on the back!

👨‍💻 Developer
===============
Built with ❤︎ by Danyl Fernandes
- Website (WIP)
- Twitter (https://twitter.com/androidanyl)
- LinkedIn (https://www.linkedin.com/in/danyl-fernandes-5bb706157/)

✳️ Citations
============
1. Not a "problem" per se, but every tick of the `CountDownTimer` is calculated using the duration of the previous tick, which is what makes the ticks inaccurate as the timer run-time goes up.
2. BetterTimer provides convenience methods (`timer.start()`, `timer.pause()`, `timer.reset()`) to make setting up a timer in your app AS EASY AS CAN BE.

📑 License
==========
Copyright 2020 Danyl Fernandes

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

