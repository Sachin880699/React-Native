# Topic

1 ) what is status bar
2 ) how t update style for status bar
3 ) hide and show status bar
4 ) Update status with button Press



# code 


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, StatusBar, Button } from "react-native";

    const App = () => {
      const [hide,setHide] = useState(false)
      const [barStyle, setBarstyle] = useState("default")
      return (
        <View style={styles.container}>
          <StatusBar
          backgroundColor="orange"
          barStyle={barStyle}
          hidden={hide}

          />
          <Button title="Togle Status Bar" onPress={()=>setHide(!hide)} />
          <Button title="Update style" onPress={()=>setBarstyle("dark-content")} />
        </View>
      )
    }

    const styles=StyleSheet.create({
      container:{
        flex:1,
        justifyContent:"center"
      },

    })
    export default App;
