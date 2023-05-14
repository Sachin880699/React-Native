# Content

1 ) Make an Array of users
2 ) Use flatlist for create list
3 ) apply style of list
4 ) Interview Questions

 
 # Array list display
 
 
 
    import React, { useState } from 'react'
    import { View, Text, TextInput, StyleSheet, Button, FlatList } from 'react-native'


    const App = () => {
      const users = [
        {
          id: 1,
          name: "sachin"
        },
        {
          id: 2,
          name: "sagar"
        },
        {
          id: 3,
          name: "Peater"
        }
        ,
        {
          id: 4,
          name: "Rohit"
        },
        {
          id: 3,
          name: "Peater"
        }
        ,
        {
          id: 4,
          name: "Rohit"
        }
      ]

      return (
        <View>
          <Text >React Native Simple Form</Text>
          <FlatList
            data={users}
            renderItem={({ item }) => <Text style={style.item}>{item.name}</Text>} keyExtractor={item => item.id}
          />
        </View>
      )
    }

    const style = StyleSheet.create({
      item: {
        fontSize: 24,
        padding: 10,
        color: "white",
        backgroundColor: "blue",
        borderColor: "red",
        borderWidth: 1,
        margin: 10
      }
    })

    export default App
