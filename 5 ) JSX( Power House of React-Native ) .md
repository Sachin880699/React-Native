
1 ) what is jsx.
2 ) Example of JSX
3 ) intresting fact about JSX
4 ) Interview Question



    import React from 'react';
    import { Button, Text, View } from 'react-native'
    const name = "sachin"
    let age = 20;
    var email = 'sachin@gmail.com'

    function fruit(){
      return 'apple'
    }
    const App = () => {
      return (
        <View>
          <Text style={{ fontSize: 30 }}>My Name Is : {name}</Text>
          <Text style={{ fontSize: 30 }}>My Name Is : {fruit()}</Text>
          <Text style={{ fontSize: 30 }}>My Name Is : {age ===29?"Aboce 20":"Unknow age"}</Text>
        </View>
      );
    };

    export default App
