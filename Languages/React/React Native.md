# React Native
_React Native is like React, but it uses native components instead of web components as building blocks._

Terminal Command to create new React Native project
`npx create-expo-app@latest`

Install dependencies
`npm install`

Run React Native app
`npx expo start`

We import `React`, and some `React Native` components
```javascript
import React from 'react';
import {Text, View} from 'react-native';
```
This function returns a single component.  
`View`: component with some styles,  
contains `Text` as a child.
```javascript
const HelloWorldApp = () => {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}>
      <Text>Hello, world!</Text>
    </View>
  );
};
```

```javascript
export default HelloWorldApp;
```

## Props
_Read only variables that used for customizing components._
Most components can be customized when they are created, with different parameters.
```javascript
const Greeting = (props: GreetingProps) => {
  return (
    <View style={styles.center}>
      <Text>Hello {props.name}!</Text>
    </View>
  );
};

<Greeting name="Rexxar" />
```

## State
```javascript
const App = () => {
  const [count, setCount] = useState(0);

  return (
    <View style={styles.container}>
      <Text>You clicked {count} times</Text>
      <Button
        onPress={() => setCount(count + 1)}
        title="Click me!"
      />
    </View>
  );
};
```