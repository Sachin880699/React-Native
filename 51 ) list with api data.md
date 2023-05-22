

# code 




    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, FlatList, StyleSheet } from 'react-native';



    const App = () => {
      const [data, setData] = useState([])

      const getAPIData = async ()=>{
        const url = "https://jsonplaceholder.typicode.com/users"
        let result = await fetch(url);
        result = await result.json();
        console.warn(result)
        if(result){
          setData(result)

        }
      }

      useEffect(()=>{
        getAPIData()
      })


      return (
       <View style={styles.container}>
        <View style={styles.dataWrapper}>

    <View style={{flex:2}}><Text style={{color:"red",fontSize:20}}>Name</Text></View>
    <View style={{flex:1}}><Text style={{color:"red",fontSize:20}}>Operation</Text></View>

    </View>

        {
          data.length?
          data.map((item)=><View style={styles.dataWrapper}>

            <View style={{flex:1}}><Text>{item.name}</Text></View>
            <Button title='Delete'  />
            <Button title='Update' />

          </View>)
          :null
        }

      </View>
      );
    };

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        padding: 10,
      },
      dataWrapper:{

        flexDirection:"row",
        justifyContent:"space-around",
        backgroundColor:"orange",
        margin:5,
        padding:8
      }

    });

    export default App
