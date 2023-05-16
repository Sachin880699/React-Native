
# Topics

1 ) Make component andhide on button press<br>
2 ) Apply useEffect Hook<br>
3 ) why need to call life cycle on Unmount<br>


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button } from "react-native";

    const App = () => {

        const [show,setShow] = useState(true)

      return (
        <View>
          <Text style={{ fontSize: 30, color: "orange" }}>Hide show</Text>
          <Button title="toggle" onPress={()=>setShow(!show)} />

          {
            show ? <Student /> : null
          }
        </View>
      )
    }

    const Student=()=>{
      return(
        <View>
        <Text style={{fontSize:30,color:"red"}}>Student</Text>
      </View>
      )
    }


    export default App;
