# Topics

1 ) Make search box and get Value<br>
2 ) Call API for search result<br>
3 ) Display search result<br>
4 ) Add style



# code 


    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, FlatList, StyleSheet, Modal, TextInput } from 'react-native';


    const App = () => {
      const [data,setData] = useState([])
      const searchUser = async (text)=>{
        const url = `http://192.168.1.3:3000/users?q=${text}`;

        let  result = await fetch(url);
        result = await result.json();
        if(result){
          setData(result)

        }
      }

      return (
        <View style={{flex:1}}>
          <TextInput style={{borderColor:"skyblue",borderWidth:1,margin:1,fontSize:20}} 
          placeholder={'Search'}
          onChangeText={(text)=>searchUser(text)}
          />

          {
            data.length ?
            data.map((item)=><View>
              <Text style={{fontSize:20}}>{item.name}</Text>
            </View>)
            :null
          }

        </View>
      );
    };

    export default App
