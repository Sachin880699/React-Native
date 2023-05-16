


# code 



    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button } from "react-native";

    const App = () => {



      return (
        <View style={styles.box}>
          <View style={styles.box1}>
            <View style={styles.InnerBox1}></View>
            <View style={styles.InnerBox1}></View>
            <View style={styles.InnerBox1}></View>
          </View>
          <View style={styles.box2}></View>
          <View style={styles.box3}></View>


        </View>
      )
    }

    const styles=StyleSheet.create({
      box:{
        flex:1,

      },
      box1:{
        flex:1,
        backgroundColor:"red"
      },
      box2:{
        flex:1,
        backgroundColor:"green"
      },
      box3:{
        flex:1,
        backgroundColor:"orange"
      },
      InnerBox1:{
        flex:1,
        backgroundColor:"skyblue",
        margin:10
      }
    })



    export default App;
