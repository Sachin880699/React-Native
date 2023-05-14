# Topics

1 ) what are the Props ?
2 ) Example of Props
3 ) Difference between state and props
4 ) Interview Question


1 ) what are the props

Ans : wehenave we want to share data one component to another component that time we use props

# pass data by props


    import React, {useState} from 'react';
    import { Alert,Button, Text, View } from 'react-native'


    const App = () => {
    const [name,setName] = useState("Hacker")



      return (
        <View>
          <Text style={{ fontSize: 30 }}>{name}</Text>
          <Button title='Press Me' onPress={()=>setName("Robot")}></Button>
          <User name={name} />
        </View>
      );
    };

    const User = (props) =>{
      console.warn(props)
      return(
        <View style={{backgroundColor:'green',padding:5}}>
          <Text style={{fontSize:20}}>{props.name}</Text>
        </View>
      );
    }


    export default App
