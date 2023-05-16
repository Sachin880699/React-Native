# Topics

1 ) Make List iwth flatlist and array<br/>
2 ) Apply style<br/>
3 ) Make component<br/>
4 ) Use Component inside list<br/>



# Code


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList } from "react-native";

    const App = () => {
      const users = [
        {
          id: 1,
          name: "sachin",
          email: "sachin@test.com"
        },
        {
          id: 2,
          name: "sagar",
          email: "sagar@test.com"
        },
        {
          id: 3,
          name: "tushar",
          email: "tushar@test.com"
        },
      ]
      return (
        <View >
          <Text style={{ fontSize: 20 }}>User</Text>
          <FlatList
            data={users}
            renderItem={({ item }) => <UserData item={item} />
            }
          />
        </View>
      );
    };

    const UserData = (props) => {
      const item = props.item
      return (
        <View style={styles.box}>
          <Text style={styles.item}>{item.name}</Text>
          <Text style={styles.item}>{item.email}</Text>
        </View>
      )
    }
    const styles = StyleSheet.create({
      item: {
        fontSize: 30,
        color: "orange",
        flex: 1,
        margin: 2,
        textAlign: "center",


      },
      box: {
        flexDirection: "row",
        borderWidth: 2,
        borderColor: "orange",
        marginBottom: 10,

      }
    })
    export default App;
