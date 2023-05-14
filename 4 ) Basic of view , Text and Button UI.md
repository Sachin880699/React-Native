# Hello world

    import React from 'react';
    import {
      Text,
      View
    } from 'react-native';

    const App = () => {
      return(

      <Text style={{fontSize:30}} > Hello</Text>

      );
    };

    export default App
   
 # Hello world with Button
 
    import React from 'react';
    import { Button, Text, View } from 'react-native'

    const App = () => {
      return (

        <View>
          <Text style={{ fontSize: 30 }}>Hello World</Text>
          <Text style={{ fontSize: 40 }}>Hello World</Text>
          <Text style={{ fontSize: 50 }}>Hello World</Text>

          <Button title='Press Me'></Button>

        </View>
      );
    };

    export default App
