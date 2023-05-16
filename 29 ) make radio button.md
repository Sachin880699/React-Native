
# Topics

1 ) make 2 TouchableOpacity with text <br>
2 ) Apply style for the radio button<br>
3 ) use state to make working radio button<br>


# Radio button code



    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button, TouchableHighlight, TouchableOpacity } from "react-native";

    const App = () => {

      const [selectRadio, SetselectRadio] = useState(1)

      return (
        <View style={styles.main}>
          <TouchableOpacity onPress={() => SetselectRadio(1)}>
            <View style={styles.radioWrapper}>
              <View style={styles.radio}>
                {
                  selectRadio === 1 ? <View style={styles.radiobg}></View> : null
                }
              </View>
              <Text style={styles.radioText}>Radio 1</Text>
            </View>
          </TouchableOpacity>

          <TouchableOpacity onPress={() => SetselectRadio(2)}>
            <View style={styles.radioWrapper}>
              <View style={styles.radio}>
                {
                  selectRadio === 2 ? <View style={styles.radiobg}></View> : null
                }
              </View>
              <Text style={styles.radioText}>Radio 1</Text>
            </View>
          </TouchableOpacity>

        </View>
      )
    }

    const styles = StyleSheet.create({
      main: {
        flex: 1,
        alignItems: "center",
        justifyContent: "center"
      },
      radioText: {
        fontSize: 20
      },
      radio: {
        height: 40,
        width: 40,
        borderColor: "black",
        borderWidth: 2,
        borderRadius: 20,
        margin: 10
      },
      radioWrapper: {
        flexDirection: "row",
        alignItems: "center"
      },
      radiobg: {
        backgroundColor: "blue",
        height: 28,
        width: 28,
        borderRadius: 20,
        margin: 4
      }
    })


    export default App;
