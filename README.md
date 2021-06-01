# react-native-navigation-container

## Table of Contents

- [About](#about)
- [Usage](#usage)
- [Contributing](./CONTRIBUTING.md)

## About <a name = "about"></a>

This is a wrapper around the react navigation - Navigation Container. It provides loading of static assests and a development navigation that maintains state after app refresh.

Features

- Load static images and fonts while splash screen is loading.
- Maintain navigation state after app refresh while in development mode

### Installing

```
yarn add react-native-navigation-container
```

```
npm install react-native-navigation-container
```

## Usage <a name = "usage"></a>

Using the Navigation Container to Load static assests

```
import React from 'react';
import { StatusBar } from 'expo-status-bar';
import NavigationContainer from 'react-native-navigation-container'

import { RootNav } from './src/navigation';

const fonts = {
  'SofiaPro-Black': require('../../assets/fonts/SofiaProBlack.otf'),
  'SofiaPro-BlackItalic': require('../../assets/fonts/SofiaProBlackItalic.otf'),
};


const assets = [
  require('../../assets/images/img1.png'),
  require('../../assets/images/img2.png'),
];

export default function App() {
  return (
    <NavigationContainer fonts={fonts} assets={assets} stickyNav={true}>
        <RootNav />
        <StatusBar backgroundColor={theme.colors.white} />
    </NavigationContainer>
  );
}
```
