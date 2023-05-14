

      import React, { useState } from 'react'
      import { View , Text, TextInput, StyleSheet, Button } from 'react-native'


      const App = ()=>{
      const [name , setName] = useState(null)
      const [email , setEmail] = useState(null)
      const [password , setPassword] = useState(null)
      const [display, setDisplay] = useState(false)


      return(

        <View>
          <Text style={styles.textName}>React Native Simple Form</Text>

          <TextInput style={styles.textInput} value={name}  onChangeText={(text)=>setName(text)} placeholder='Enter Name' ></TextInput>

          <TextInput style={styles.textInput} value={email}  onChangeText={(text)=>setEmail(text)} placeholder='Enter Email' ></TextInput>
          <TextInput style={styles.textInput} secureTextEntry={true} value={password}  onChangeText={(text)=>setPassword(text)} placeholder='Enter Password' ></TextInput>

        <View style={{marginBottom:10}}>
          <Button title='Print Details' onPress={()=>setDisplay(true)} />

          </View>
          <Button title='Clear Details' onPress={()=>setDisplay(false)} />


          {
          display ?
          <View >
            <Text style={{fontSize:20}}>Name : {name}</Text>
            <Text style={{fontSize:20}}>Email : {email}</Text>
            <Text style={{fontSize:20}}>Password : {password}</Text>
          </View>
          : null
        }

        </View>


      )
    }

    const styles = StyleSheet.create({
      textInput: {
        fontSize:40,
        color:"blue",
        borderColor:"red",
        borderWidth:2,
        margin:10

      },
      textName :{
        fontSize:30

      }
    })

    export default App
