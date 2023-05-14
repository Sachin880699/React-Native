# Topics 

1 ) What is the state ?
2 ) Example of state
3 ) How to update state ?
4 ) Difference between state and variable
5 ) Interview Questions


# What is state

state is information holder inside the component info like address , name, age


# example of state


    import React, {useState} from 'react';
    import { Alert, Button, Text, View } from 'react-native'


    const App = () => {
      const [name , setName] = useState("sachin")
      return (
        <View>
          <Text style={{ fontSize: 30 }}>{name}</Text>
        </View>
      );
    };
    export default App
    
# button press change name help of the state


    import React, {useState} from 'react';
    import { Alert, Button, Text, View } from 'react-native'


    const App = () => {
      const [name , setName] = useState("sachin")

      function testname(){
        setName("Pawar")
      }

      return (
        <View>
          <Text style={{ fontSize: 30 }}>{name}</Text>
          <Button title='update name' onPress={testname}></Button>
        </View>
      );
    };
    export default App
    
# Note

1 ) we cannot share state data
2 ) we can share probs data
