# Topics

1 ) why default button not support style <br>
2 ) Alternative of button react-native<br>
3 ) style with Touchable Highlight<br>
4 ) Make different type of button with style<br>

# create button with TouchableHighlight


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button, TouchableHighlight } from "react-native";

    const App = () => {

      return (
        <View style={styles.main}>
          <TouchableHighlight>
            <Text style={styles.button}> Button</Text>
          </TouchableHighlight>

          <TouchableHighlight>
            <Text style={styles.button1}> Delete</Text>
          </TouchableHighlight>

        </View>
      )
    }

    const styles = StyleSheet.create({
      main: {
        flex: 1
      },
      button: {
        backgroundColor: "#bbb",
        color: "white",
        fontSize: 24,
        textAlign: "center",
        padding: 10,
        margin: 10,
        borderRadius: 10,
        shadowColor: "red",
        elevation: 10,
        shadowOpacity: 1
      },
      button1: {
        backgroundColor: "red",
        color: "white",
        fontSize: 24,
        textAlign: "center",
        padding: 10,
        margin: 10,
        borderRadius: 10,
        shadowColor: "red",
        elevation: 10,
        shadowOpacity: 1
      }

    })



    export default App;
