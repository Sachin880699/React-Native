# Topic 

1 ) use of pressable<br>
2 ) add style to the button<br>
3 ) check all Event<br>


# code for long press 

    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, ActivityIndicator, Button, Modal, Pressable, } from "react-native";

    const App = () => {
      return (
        <View style={styles.main}>
          <Pressable 
          onPress={()=>console.warn("normal on press")}
          onLongPress={()=>console.warn("Long Press")}
          onPressIn={()=>console.warn("Press In")}
          onPressOut={()=>console.warn("Press Out")}

          >
            <Text style={styles.pressableBtn}>Pressable</Text>
          </Pressable>
        </View>
      )
    }

    const styles=StyleSheet.create({
      main:{
        flex:1,
        justifyContent:"center"
      },
      pressableBtn:{
        backgroundColor:"blue",
        color:"white",
        padding:10,
        margin:10,
        borderRadius:10,
        fontSize:30,
        textAlign:"center",
        shadowColor:"black",
        elevation:10
      }
    })
    export default App;
