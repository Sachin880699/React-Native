# TOPIC

1 ) Make function to call API
2 ) Use FlatList to render Data
3 ) Add Style and ScrollView


# Code


    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, TextInput, ScrollView, FlatList } from 'react-native';

    const App = () => {

        const [ data,setData] = useState([])

        const getAPIData = async ()=>{
          const url = "https://jsonplaceholder.typicode.com/posts"
          let result = await fetch(url);
          result = await result.json();
          setData(result)
        }
        useEffect(()=>{
          getAPIData()
        },[])

      return (
        <View>
          <Text style={{ fontSize: 30 }}>API Call</Text>
          {
            data.length?
            <FlatList

            data = {data}
            renderItem = {({item})=><View style={{borderBottomColor:"orange",borderBottomWidth:1,padding:10}}>
            <Text style={{ fontSize: 24, backgroundColor:"#ccc" }}>{item.id}</Text>
            <Text style={{ fontSize: 18 }}>{item.title}</Text>
            <Text style={{ fontSize: 20 }}>{item.body}</Text>
            </View>}

            />
            :null
          }

          </View>
      );
    };

    export default App
