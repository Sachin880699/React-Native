
1 ) Make an Array of users </br>
2 ) Use map function for create list</br>
3 ) apply style of list</br>
4 ) need scrollView to scroll list</br>



# list with function

    import React from "react";
    import { FlatList, StyleSheet, Text, View } from 'react-native'
    import style from "./style";

    const App = () => {
      const items = [
        {
          name: "sachin",
          address: "pune"
        },
        {
          name: "Sagar",
          address: "Mumbai"
        },
        {
          name: "sachin",
          address: "pune"
        },
      ];

      return (
        <View style={styles.container}>
          <FlatList
            data={items}
            renderItem={({ item }) => (
              <View style={styles.item}>
                <Text>{item.name}</Text>
                <Text>{item.address}</Text>
              </View>
            )}

          />
        </View>
      );
    };
    const styles = StyleSheet.create({
      container:{
        flex:1,
      },
      item: {
        padding:10,
        borderRadius:5,
        backgroundColor:"lightgray",
      }
    })
    export default App
    
    
# List with map function



    import React from "react";
    import { FlatList, ScrollView, StyleSheet, Text, View } from 'react-native'
    import style from "./style";

    const App = () => {
      const items = [
        {
          name: "sachin",
          address: "pune"
        },
        {
          name: "Sagar",
          address: "Mumbai"
        },
        {
          name: "sachin",
          address: "pune"
        },
      ];

      return (
        <View >
          <ScrollView>
            {
              items.map((item)=>
              <View style={styles.item}>
                <Text>{item.name}</Text>
                <Text>{item.address}</Text>
              </View>
              )
            }
          </ScrollView>
        </View>
      );
    };

    const styles = StyleSheet.create({
      item:{
        fontSize:24,
        padding:10,
        color: "#fff",
        backgroundColor:"blue",
        borderColor: "black",
        borderWidth:1,
        margin:10

      }
    })


    export default App
