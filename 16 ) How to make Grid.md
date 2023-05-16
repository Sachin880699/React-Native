# Topics

1 ) Add Text items for static Grid
2 ) Add style to make the grid
3 ) make dynamic grid
4 ) interview question


# static grid


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList } from "react-native";

    const App = () => {

      const numberOfColumns = 2;

      return (
        <View >
          <Text style={{fontSize:31}}>Grid with Dynamic Daata</Text>
          <View style={{flex:1,flexDirection:"row",flexWrap:'wrap'}}>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          <Text style={styles.item}>Sachin</Text>
          </View>
        </View>
      );
    };

    const styles = StyleSheet.create({
      item:{
          fontSize:25,
          backgroundColor:"blue",
          color:"#fff",
          margin:5,
          padding:5,
          width:120,
          height:120,
          textAlignVertical:"center",
          textAlign:"center"
      }
    })

    export default App;
