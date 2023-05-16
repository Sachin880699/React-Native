
# Point

1 ) Make SectionData with Array<br/>
2 ) Use SectionList<br/>
3 ) Render Items and Header<br/>


# code 


    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, FlatList, SectionList } from "react-native";

    const App = () => {
      const users = [
        {
          id: 1,
          name: "sachin",
          data: ["python", 'php', 'react-js']
        },
        {
          id: 2,
          name: "sagar",
          data: ["JavaScript", "HTML"]
        },
        {
          id: 3,
          name: "tushar",
          data: ['CSS', 'Bootstrap']
        },
      ]
      return (
        <View >
          <Text style={{ fontSize: 20 }}>User</Text>
          <SectionList
            sections={users}
            renderItem={({ item }) => <Text style={{ fontSize: 20, marginLeft: 20 }}>{item}</Text>}
            renderSectionHeader={({ section: { name } }) => (
              <Text style={{ fontSize: 25, color: "red" }}>{name}</Text>
            )
            }
          />
        </View>
      );
    };

    export default App;
