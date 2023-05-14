
# Topics

1 ) Make Text input and define the state.
2 ) Apply Style in Text input
3 ) Get Text input value on change
4 ) Clear Text input value
5 ) interview questions


# create input box and handel that



    import React, { useState } from 'react';
    import { Button, Text, TextInput, View, StyleSheet } from 'react-native'
    import Exstyles from "./style"

    const App = () => {

      const [name , setName] = useState("Sachin")
      return (
        <View>
          <Text style={styles.text}>Name : {name}</Text>
          <TextInput  placeholder='Enter Your Name' value={name} onChangeText={(text)=>setName(text)}
          style={styles.textInput}
          />
          <Button title='Clear Me' onPress={()=>setName("")}></Button>

        </View>
      );
    };

    const styles = StyleSheet.create({

      textInput: {
        fontSize:18,
        color:"red",
        borderWidth:2,
        borderColor:"red",
        margin:10
      },
      text:{
        fontSize:40
      }


    })

    export default App
