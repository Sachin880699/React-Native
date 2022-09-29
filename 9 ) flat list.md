

# https://reactnative.dev/docs/flatlist


    import React from 'react';
    import {SafeAreaView , FlatList ,Text ,  View, StyleSheet} from 'react-native';


    const DATA = [
      {
        "id":1,
        "title":"First Name",
      },
      {
        "id":2,
        "title":"Second Name",
      },

    ];

    const Item = ({title}) =>(
      <View style={styles.item}>
        <Text style={styles.title}>{title}</Text>
      </View>
    );



    const App = () => {
      const renderItem = ({item}) => (
        <Item  title={item.title}/>
      );



      return (
        <SafeAreaView>
          <FlatList
          data = {DATA}
          renderItem = {renderItem}
          keyExtractor={item => item.id}
          />

        </SafeAreaView>
      );
    }

    const styles = StyleSheet.create({
      title:{
        fontSize:32
      },
      item:{
        backgroundColor:"#f9c2ff",
        padding:20,
        marginVertical:8,
        marginHorizontal:16,
      }

    })

    export default App;
