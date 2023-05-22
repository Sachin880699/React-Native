
# Call Basic Post API


    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, TextInput, ScrollView, FlatList } from 'react-native';

    const App = () => {

      const saveAPIData = async () => {
        const url = "https://reqres.in/api/users"
        const data ={
          name:"morpheus",
          job:"leader"
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
          <Button title='Save Data' onPress={saveAPIData} />
        </View>
      );
    };

    export default App
