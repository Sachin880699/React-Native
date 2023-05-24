# Topic

1 ) what if ref <br>
2 ) How to use ref <br>
3 ) Focus with ref<br>
4 ) Update style with ref <br>

# code 


    import React, { useEffect, useState , useRef} from 'react';
    import { Text, View, Button, FlatList, StyleSheet, Modal, TextInput } from 'react-native';


    const App = () => {
      const input = useRef();
      const updateInput = ()=>{
        console.warn("call")
        input.current.focus()
        input.current.setNativeProps({
          fontSize:24,
          color:"green"
        })
      }

      return (
        <View style={styles.container}>
          <TextInput ref={input} style={styles.input} placeholder='Enter Name' />
          <TextInput style={styles.input} placeholder='Enter password ' />
          <Button title='Update' onPress={updateInput} />
        </View>
      );
    };

    const styles = StyleSheet.create({
      container:{
        flex:1,
        padding:16
      },
      input:{
        borderColor:"skyblue",
        borderWidth:2,
        margin:10
      }
    })



    export default App

