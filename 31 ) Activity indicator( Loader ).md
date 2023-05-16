# Topic

1 ) Use of activity indicator<b>
2 ) Common Props<b>
3 ) Hide and how with button<b>
  
# Code
  
  
  
  
    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, ActivityIndicator, Button,  } from "react-native";

    const App = () => {
      const [show , setShow] = useState(false)
      const displayLoader=()=>{
        setShow(true)
        setTimeout(()=>{
          setShow(false)
        },4000);
      }

      return (
        <View  style={styles.main}>

         <ActivityIndicator size={100} color="green"  animating={show} />
         <Button title="show loader" onPress={displayLoader} />


        </View>
      )
    }

    const styles = StyleSheet.create({
      main:{
        flex:1,
        alignItems:"center",
        justifyContent:"center"
      }
    })




    export default App;
