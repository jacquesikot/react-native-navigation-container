# react-native-navigation-container

[![npm version](https://badge.fury.io/js/react-native-navigation-container.svg)](https://badge.fury.io/js/react-native-navigation-container)
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier)

## Table of Contents

- [About](#about)
- [Usage](#usage)
- [Contributing](./CONTRIBUTING.md)

## About <a name = "about"></a>

The goal of `react-native-navigation-container` is to provide a convinient method to load static fonts and assets during the app splash screen and to provide useful utility features for better expo and react-native devlopment.

## Features

- Load static images and fonts while splash screen is showing.
- Maintain navigation state after app refresh while in development mode.

## Setup

This library is available on npm, install it with: `npm i react-native-navigation-container` or `yarn add react-native-navigation-container`.

## Usage <a name = "usage"></a>

Since `react-native-navigation-container` is an extension of the original react navigation `NavigationContainer`, it works in a similar fashion [react navigation - navigation container](https://reactnavigation.org/docs/navigation-container/).

1. Import react-native-navigation-container:

```javascript
import NavigationContainer from 'react-native-navigation-container';
```

2. Wrap root navigation with Navigation container:

```javascript
export default function App() {
  return (
    <NavigationContainer>
      <RootNav />
      <StatusBar backgroundColor={theme.colors.white} />
    </NavigationContainer>
  );
}
```

3. Prepare fonts and assets to be loaded:

```javascript
const fonts = {
  'SofiaPro-Black': require('../../assets/fonts/SofiaProBlack.otf'),
  'SofiaPro-BlackItalic': require('../../assets/fonts/SofiaProBlackItalic.otf'),
};

const assets = [
  require('../../assets/images/img1.png'),
  require('../../assets/images/img2.png'),
];
```

4. Add fonts and assets to navigation container:

```javascript
export default function App() {
  return (
    <NavigationContainer fonts={fonts} assets={assets}>
      <RootNav />
      <StatusBar backgroundColor={theme.colors.white} />
    </NavigationContainer>
  );
}
```

5. Optionally set the `stickyNav` prop:

```javascript
export default function App() {
  return (
    <NavigationContainer fonts={fonts} assets={assets} stickyNav={true}>
      <RootNav />
      <StatusBar backgroundColor={theme.colors.white} />
    </NavigationContainer>
  );
}
```

## A complete example

```javascript
import React from 'react';
import { StatusBar } from 'expo-status-bar';
import NavigationContainer from 'react-native-navigation-container;

import { RootNav } from './src/navigation';

export default function App() {
  return (
    <NavigationContainer fonts={fonts} assets={assets} stickyNav={true}>
        <RootNav />
        <StatusBar style='auto' />
    </NavigationContainer>
  );
}
```

## Availble props

| Name | Type | Description
|
| ---------------|-----------------|-------------------------------------------------------------

---

| fonts | object | Fonts to be loaded into app
| assests | array | Assets to be loaded into app
| stickyNav | boolean | Maintains navigation state after app refresh - only in dev mode
