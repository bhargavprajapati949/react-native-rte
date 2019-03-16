# React Native Rich Text Editor

A rich text editor for React Native based on Quill.js.

Compatible with iOS and Android.

## Installation

Install React Native Rich Text Editor using npm:

```
npm install react-native-rte --save
```

Link react-native-webview:

```
react-native link react-native-webview
```

## Example

```jsx
import React, { Component } from 'react';
import { SafeAreaView, KeyboardAvoidingView } from 'react-native';
import { RichText, Bold, Italic, OrderedList, UnorderedList, Link, Media } from 'react-native-rte'

export default class App extends Component {
  selectMedia() {
    // Base64 Data
    return 'data:image/jpeg;base64,BASE64DATA'

    // Or an image URL
    return 'http://example.com/image.jpg'
  }

  render() {
    return (
      <SafeAreaView style={{flex:1, backgroundColor: '#fff'}}>
        <KeyboardAvoidingView style={{flex:1}} behavior={'padding'}>
          <RichText>
            <RichText.Editor />
            <RichText.Toolbar>
              <Bold />
              <Italic />
              <OrderedList />
              <UnorderedList />
              <Link />
              <Media onPress={this.selectMedia.bind(this)} />
            </RichText.Toolbar>
          </RichText>
        </KeyboardAvoidingView>
      </SafeAreaView>
    )
  }
}
```
