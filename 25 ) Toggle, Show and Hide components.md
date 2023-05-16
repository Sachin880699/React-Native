
# Topic

1 ) Make Componet <br>
2 ) Button and state for toggle component<br>


# Hide/Show Component


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList, Button } from "react-native";

    const App = () => {
      const [show, setShow] = useState(true)

      return (
        <View>
          <Text style={{ fontSize: 30, color: "orange" }}>Hide show</Text>
          <Button title="Hide" onPress={() => setShow(false)} />
          <Button title="Show" onPress={() => setShow(true)} />

          {
            show == true ? <User /> : null
          }

        </View>
      )
    }

    const User = () => {
      return (
        <View>
          <Text style={{ fontSize: 30, color: "green" }}>User Component</Text>

        </View>
      )
    }

    export default App;
