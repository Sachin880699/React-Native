
1 ) by flex box we can set height and width to box . by using flex UI will become responsive

    import React from 'react';
    import {View, StyleSheet} from 'react-native';

    const App = () => {
      return (
        <View style={{flex:1, alignItems:"center",flexDirection:"row"}}>
          <View style={{width:150,height:150,backgroundColor:"red"}}></View>
          <View style={{width:150,height:150,backgroundColor:"green"}}></View>
          <View style={{width:150,height:150,backgroundColor:"blue"}}></View>

        </View>
      );
    }

    const styles = StyleSheet.create({})

    export default App;
