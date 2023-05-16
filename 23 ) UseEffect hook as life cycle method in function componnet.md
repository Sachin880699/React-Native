
# Topics

1 ) What is useEffect hook ?<br/>
2 ) How to use if.<br/>
3 ) useEffect for mounting phase<br/>
4 ) useEffect as componentDidMount<br/>


# code



    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button } from "react-native";

    const App = () => {
      const [count,setCount] = useState(0)
      useEffect(()=>{
        console.warn("Hello")
      },[])

      return (
        <View >
          <Text style={{ fontSize: 30 }}>User {count}</Text>
          <Button title="UpdateCount" onPress={()=>setCount(count + 1)} />

        </View>
      );
    };



    export default App;
