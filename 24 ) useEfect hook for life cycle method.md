# Topics

1 ) useEffect hook as componentDidUpdate ? <br>
2 ) Define state and button<br>
3 ) useEffect only for specific state<br>
4 ) useEffect only for specific props<br>


# when we want to call useEffect when useState call only that time we do like this

    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button } from "react-native";

    const App = () => {
      const [count, setCount] = useState(0);
      const [data, setData] = useState(100)
      useEffect(() => {
        console.warn(count)
      }, [count]) // Jeva use state call hoil jeva define use effect pan call hoil

      return (
        <View >
          <Text style={{ fontSize: 30 }}>number is : {count} {data} </Text>
          <Button title="UpdateCount" onPress={() => setCount(count + 1)} />
          <Button title="UpdateData" onPress={() => setData(count + 1)} />
        </View>
      );
    };

    export default App;
    
# Another


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button } from "react-native";

    const App = () => {
      const [count, setCount] = useState(0);
      const [data, setData] = useState(100)
      // useEffect(() => {
      //   console.warn(count)
      // }, [count]) // Jeva use state call hoil jeva define use effect pan call hoil
      return (
        <View >
          <Text style={{ fontSize: 30 }}>number is : {count} {data} </Text>
          <Button title="UpdateCount" onPress={() => setCount(count + 1)} />
          <Button title="UpdateData" onPress={() => setData(count + 1)} />

          <User info={{data,count}}/>
        </View>
      );
    };
    const User=(props)=>{
      console.warn(props.info)
      useEffect(()=>{

      })
      return(
        <View>
          <Text style={{fontSize:30,color:"orange"}}>User Component</Text>
        </View>
      )
    }

    export default App;
