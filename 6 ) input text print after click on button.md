____________________ App.js ____________________



    import React , {useState} from 'react';
    import {View, StyleSheet ,Text , TextInput , Button} from 'react-native';

    const App = () => {
      const [text ,setText] = useState("")
      const [inputname , setInputname] = useState("")

      function name(){
        setInputname(text)
      }

      return (
        <View>
          <Text style={{fontSize:30}}>Hello this is my first app</Text>
          <Text style={{color:"red"}} >───────────────────────────────────</Text>

          <TextInput placeholder='Enter Age' onChangeText={(text)=>setText(text)}></TextInput>
          <Button onPress={name} title='CLick me' />

          <Text style={{fontSize:30}}>{inputname}</Text>

        </View>
      );
    }

    const styles = StyleSheet.create({})

    export default App;
