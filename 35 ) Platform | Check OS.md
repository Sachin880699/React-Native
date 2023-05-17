# TOpic

1 ) what is platform
2 ) how to check platform
3 ) Apply conditions with platforms


# code 


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, StatusBar, Button, Platform } from "react-native";

    const App = () => {
      return (
        <View  >
          <Text style={{fontSize:20}}>Platform: {Platform.OS}</Text>
          {
            Platform.OS==="android" ?
            <View style={{backgroundColor:"green",height:100,width:100}}></View>
            :
            <View style={{backgroundColor:"red",height:100,width:100}}></View>
          }



        </View>
      )
    }


    export default App;
