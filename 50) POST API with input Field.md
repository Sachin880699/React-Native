# Topics

1 ) Make input Fields<br>
2 ) store input field data in state<br>
3 ) write code to call post API and test<br>


# code 


    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, TextInput, ScrollView, FlatList } from 'react-native';

    const App = () => {
      const [name , setName] = useState("")
      const [job, setJob] = useState("")
      const saveAPIData = async () => {
        const url = "https://reqres.in/api/users"
        const data ={
          name:name,
          job:job
        }
        let result = await fetch(url, {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body:JSON.stringify(data)
        })
        result = result.json();
        console.warn(result)
      }

      return (
        <View>
          <Text style={{fontSize:30,color:"red"}}>Enter Name</Text>
          <TextInput placeholder='Enter The Name' onChangeText={(text) => setName(text)} style={{borderColor:"black",borderBottomWidth:2,borderLeftWidth:2,borderRightWidth:2,borderTopWidth:2,borderRadius:9}}  /> 
          <Text style={{fontSize:30,color:"red"}}>Enter Job</Text>
          <TextInput placeholder='Enter Jon' onChangeText={(text) => setJob(text)} style={{borderColor:"black",borderBottomWidth:2,borderLeftWidth:2,borderRightWidth:2,borderTopWidth:2,borderRadius:9, marginTop:10}}  /> 
          <View style={{marginTop:10}}>
          <Button title='Save Data' onPress={saveAPIData} />
          </View>
        </View>
      );
    };

    export default App
