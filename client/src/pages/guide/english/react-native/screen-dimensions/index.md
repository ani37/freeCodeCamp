---
title: Screen Dimensions
---
## React Native - Screen Dimensions

React Native uses Dots Per Inch (DPI) to measure the sizing of the User Interface (UI) and anything displayed on the UI. This type of measurement allows an application to look uniform accross various screen sizes and pixel densities.

For standard use cases, applications can be developed without having to know the specifics of the user's device (eg pixel density) since the UI elements will scale automatically. When it is required, there are APIs availabel such as `PixelRatio` for finding out about the pixel density of the users device.

To get the window or screen height/width of a users device, React Native has an API called `Dimensions`.

```js
import { Dimensions } from 'react-native';
```

Here are the methods that the `Dimensions` API provides:
 
```js
Dimensions.get('window').height;
Dimensions.get('window').width;
Dimensions.get('screen').height;
Dimensions.get('screen').width;
```

What makes React-Native so attractive to developers is being able to write code, and have it run on multiple devices (iPhone, iPad, Pixel, etc ...). The use of the Dimensions API enables developers to write modular code to be used across multiple devices. 

for example if you wanted a screen to looka certain way on an iPad vs a phone simple math can be done to apply the proper styling.


```js
const { width, height } = Dimensions.get('window');
const TABLET_RATIO = 1.6;
const ASPECT_RATIO = height/width;
 
 // later on in the view this can be applied with a ternary 
  <FancyView
    style={(ASPECT_RATIO > TABLET_RATIO) ? styles.phone : styles.ipad }
  ></FancyView>
 
```

**Note: There have been some known issues in the past with the Dimensions API such as not returning the correct information when a user rotates their device. It's best to make sure you test this on actual devices before deploying an application.**
