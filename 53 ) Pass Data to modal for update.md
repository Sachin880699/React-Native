# Topics

1 ) Make modal and add style <br>
2 ) Open and close modal on button <br>
3 ) Pass Data to modal <br>



# code 


    import React, { useEffect, useState } from 'react';
    import { Text, View, Button, FlatList, StyleSheet, Modal } from 'react-native';



    const App = () => {
      const [data, setData] = useState([])
      const [showModal, setshowModal] = useState(false)

      const [selectedUser, setSelectedUser] = useState(undefined)


      const getAPIData = async () => {
        const url = "http://192.168.1.3:3000/users"
        let result = await fetch(url);
        result = await result.json();
        // console.warn(result)
        if (result) {
          setData(result)

        }
      }

      const deletePost = (id) => {

        const url = `'http://192.168.1.3:3000/users/${id}`;
        fetch(url, {
          method: "DELETE",
        }).then((response) => {
          console.warn(response.status)
          if (response.status === 200) {
            console.warn("User success deleted")
          } else {
            console.log("Error deleting post:", response.status);
          }
        });
      };

      useEffect(() => {
        getAPIData();

      })

      const updateUser = (data) => {
        setshowModal(true)
        setSelectedUser(data)
      }


      return (
        <View style={styles.container}>
          <View style={styles.dataWrapper}>
            <View style={{ flex: 2 }}><Text style={{ color: "red", fontSize: 20 }}>Name</Text></View>
            <View style={{ flex: 1 }}><Text style={{ color: "red", fontSize: 20 }}>Operation</Text></View>
          </View>

          {
            data.length ?
              data.map((item) => <View style={styles.dataWrapper}>

                <View style={{ flex: 1 }}><Text>{item.name}</Text></View>
                <Button title='Delete' onPress={() => deletePost(item.id)} />
                <Button title='Update' onPress={() => updateUser(item)} />

              </View>)
              : null
          }
          <Modal visible={showModal} transparent={true}>
            <UserModal setshowModal={setshowModal} selectedUser={selectedUser} />
          </Modal>

        </View>
      );
    };

    const UserModal = (props) => {
      console.warn(props.selectedUser)

      return (
        <View style={styles.centeredView}>
          <View style={styles.modalView}>
            <Text>{props.selectedUser.name}</Text>
            <Button title='CLOSE' onPress={() => props.setshowModal(false)} />
          </View>
        </View>
      )
    }

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        padding: 10,
      },
      dataWrapper: {

        flexDirection: "row",
        justifyContent: "space-around",
        backgroundColor: "orange",
        margin: 5,
        padding: 8
      },
      centeredView: {
        flex: 1,
        justifyContent: "center",
        alignItems: "center",
      },
      modalView: {
        backgroundColor: "#fff",
        padding: 40,
        borderRadius: 10,
        shadowColor: "#000",
        shadowOpacity: 0.80,
        elevation: 5
      }

    });

    export default App
