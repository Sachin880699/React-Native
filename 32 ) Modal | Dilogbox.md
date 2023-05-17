# Topic

1 ) Import button and modal <br>
2 ) add style to button and modal <br>
3 ) show and hide modal with state<br>




# popup modal code



    import React, { useState, useEffect } from "react";
    import { View, Text, StyleSheet, ActivityIndicator, Button, Modal, } from "react-native";

    const App = () => {

      const [show,setShow] = useState(false)


      return (
        <View style={styles.main}>
          <Modal
            transparent={true}

            visible={show}
          >
            <View style={styles.centeredView}>
              <View style={styles.modalView}>
                <Text style={styles.modelText}>Hello Coder</Text>
                <Button title="OK" onPress={()=>setShow(false)} />
              </View>
            </View>
          </Modal>

          <View style={styles.buttonView}>
            <Button title="Open Modal" onPress={()=>setShow(true)} />
          </View>



        </View>
      )
    }

    const styles = StyleSheet.create({
      buttonView: {


      },
      main: {
        flex: 1,
        justifyContent: "flex-end"
      },
      centeredView: {
        flex: 1,
        justifyContent: "center",
        alignItems: "center",

      },
      modalView: {
        backgroundColor: "skyblue",
        padding: 40,
        borderRadius: 20,
        shadowColor: "black",
        elevation: 10
      },
      modelText: {
        fontSize: 30
      }
    })



    export default App;
