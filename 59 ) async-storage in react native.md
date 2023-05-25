# Topic

1 ) What is async-storage<br>
2 ) install async-storage<br>
3 ) Use async-storage<br>
  * ) set data
  * ) GET data
  * ) Remove data


# LINK 

1 ) go to  ( [https://reactnative.dev/docs/asyncstorage](https://reactnative.directory/?search=storage) )

2 ) click on ( @react-native-async-storage/async-storage )

3 ) https://react-native-async-storage.github.io/async-storage/docs/install/

# install it

1 ) npm install @react-native-async-storage/async-storage



# code 



    import React, { useEffect, useState , useRef} from 'react';
    import { Text, View, Button, FlatList, StyleSheet, Modal, TextInput } from 'react-native';
    import  AsyncStorage from "@react-native-async-storage/async-storage"

    const App = () => {
      const [showName , setshowName] = useState(undefined)
      const setData = async ()=>{
        await AsyncStorage.setItem("name","hacekr pawar")
      }

      const getData = async ()=>{
       const name =  await AsyncStorage.getItem("name")
       console.warn(name)
       setshowName(name)
      }

      const removeData = async ()=>{
        await AsyncStorage.removeItem("user")
        setshowName()
      }

      return (
        <View style={styles.container}>
            <Text style={{fontSize:30}}>{showName}</Text>
          <View style={{marginBottom:10}}><Button title='setData' onPress={setData} /></View>
          <View style={{marginBottom:10}}><Button title='getData' onPress={getData} /></View>
          <View style={{marginBottom:10}}><Button title='Remove data' onPress={removeData} /></View>

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
