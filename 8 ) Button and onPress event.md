1 ) how to make a button
2 ) change the color of the button
3 ) call function on button press
4 ) pass data to function from event 
5 ) Interview Questions


# make a button

    import React from 'react';
    import { Button, Text, View } from 'react-native'

    const App = () => {
      return (
        <View>
          <Text style={{ fontSize: 30 }}>Hello</Text>

          <Button title='Press Me' ></Button>

        </View>
      );
    };

    export default App


# change button color

 <Button title='Press Me' color={"red"}></Button>



# function call



    import React from 'react';
    import { Alert, Button, Text, View } from 'react-native'

    const fruit = () =>{
      console.warn("Function call")
    }

    const App = () => {
      return (
        <View>
          <Text style={{ fontSize: 30 }}>Hello</Text>

          <Button title='Press Me' color={"red"} onPress={()=>fruit()} ></Button>

        </View>
      );
    };
    export default App
    
    
 # pass value from onpress button to function
 
    import React from 'react';
    import { Alert, Button, Text, View } from 'react-native'

    const fruit = (name) =>{
      console.warn(name)
    }

    const App = () => {
      return (
        <View>
          <Text style={{ fontSize: 30 }}>Hello</Text>

          <Button title='Press Me' color={"red"} onPress={()=>fruit("sachin")} ></Button>

        </View>
      );
    };
    export default App
    

