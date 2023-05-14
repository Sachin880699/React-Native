
# Basic Style in React Native

1 ) style type in react native
2 ) Inline Style
3 ) Internal Style
4 ) External Style
5 ) Basic But important style properties
6 ) Interview question


# Inline Style

    <Text style={{ fontSize: 40, color:"red" }}>Sachin</Text>
    
# Internal Style

    import React from 'react';
    import { StyleSheet, Text, View } from 'react-native'


    const App = () => {
      return (
        <View>
          <Text style={styles.textBox}>Sachin</Text>
        </View>
      );
    };

    const styles = StyleSheet.create({
      textBox:{
        color:"blue",
        backgroundColor:"green",
        fontSize:30
      }
    })
    export default App
    
# External stylesheet


<b> app.js </b>

    import React from 'react';
    import { Text, View } from 'react-native'
    import Exstyles from "./style"

    const App = () => {
      return (
        <View>
          <Text style={Exstyles.textBox}>Sachin</Text>
        </View>
      );
    };

    export default App
    
    
<b>style.js </b>

    import { StyleSheet } from "react-native"

    export default Exstyles = StyleSheet.create({
        textBox:{
          color:"blue",
          backgroundColor:"green",
          fontSize:30
        }
      })


