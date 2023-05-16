# Topics

1 ) Make an array of skills<br>
2 ) Appply map over the radio button<br>
3 ) Update state with skill<br>



# Dynamic Radio button ( Depend on previus )




    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button, TouchableHighlight, TouchableOpacity } from "react-native";

    const App = () => {

      const [selectRadio, SetselectRadio] = useState(1)
      const skills = [
        {
          name:"Java",
          id:1
        },
        {
          name:"Python",
          id:2
        },
        {
          name:"JavaScript",
          id:3
        },
        {
          name:"C++",
          id:4
        },
      ]

      return (
        <View style={styles.main}>
          {
            skills.map((item,index)=>
            <TouchableOpacity
            key={index}
            onPress={() => SetselectRadio(item.id)}>
            <View style={styles.radioWrapper}>
              <View style={styles.radio}>
                {
                  selectRadio === item.id ? <View style={styles.radiobg}></View> : null
                }
              </View>
              <Text style={styles.radioText}>{item.name}</Text>
            </View>
          </TouchableOpacity>
    )
          }

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
