# Topic

1 ) Make function to call API <br>
2 ) Use map function to render Data<br>
3 ) Add style and scrollView<br>


# Code


    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, TextInput, ScrollView } from 'react-native';



    const App = () => {
      const [data, setData] = useState([])
      const getAPIData = async () => {
        const url = "https://jsonplaceholder.typicode.com/posts";
        let result = await fetch(url);
        result = await result.json();
        setData(result);
      }
      useEffect(() => {
        getAPIData();
      }, []);




      return (
        <ScrollView>
          <Text style={{ fontSize: 30 }}>API Call</Text>
          {data.length ?
            data.map((item) => <View style={{ padding: 10, borderBottomColor: "#ccc", borderBottomWidth: 2 }}>
              <Text style={{ fontSize: 20, backgroundColor: "#ddd" }}>ID :  {item.id}</Text>
              <Text style={{ fontSize: 20 }}>Title :  {item.title}</Text>
              <Text style={{ fontSize: 20 }}>Body :  {item.body}</Text>
            </View>)
            :
            null
          }
        </ScrollView>
      );
    };



    export default App
