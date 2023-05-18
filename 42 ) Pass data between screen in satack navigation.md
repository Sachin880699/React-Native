# Topic

1 ) Pass static data from one screen to another screen <br>
2 ) Access data and display data <br>
3 ) Pass text input data in screens <br>



# Login.js

    import {Text,View, Button, TextInput} from 'react-native';
    import { useState} from "react"

    export const Login = (props)=>{
        const [name,setName] = useState("")
        const age = 26;


        return(
          <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
            <Text style={{fontSize:30}}>Login Screen</Text>
            <TextInput
            style={{fontSize:20,borderColor:"#000",borderWidth:2}}
             onChangeText={(text)=>setName(text)} placeholder='Enter the Name' />
            <Button title="Go to Home Page" 
            onPress={()=>props.navigation.navigate("Home",{age,name})} 

            />
          </View>
        )
      }


# app.js


    import React from 'react';
    import {Text,View, Button, TextInput} from 'react-native';
    import {NavigationContainer} from "@react-navigation/native";
    import  {createNativeStackNavigator} from "@react-navigation/native-stack"
    import { Login } from './components/Login';
    import {Home} from "./components/Home"


    const Stack = createNativeStackNavigator();

    const App = () => {
    const btnAction =()=>{
      console.warn("btn Press")
    }
     return(
        <NavigationContainer>
          <Stack.Navigator
          screenOptions={{
            title:"User Login",
            headerStyle:{
              backgroundColor:"blue",

            },
            headerTintColor:"#fff",
            headerTitleStyle:{
              fontSize:25
            }

          }}
          >

          <Stack.Screen name="Login" component={Login} 
          options={{
            headerTitle:()=><Button title="Left" onPress={btnAction} />,
            headerRight:()=><Header />,
            title:"User Login",
            headerStyle:{
              backgroundColor:"skyblue",

            },
            headerTintColor:"#fff",
            headerTitleStyle:{
              fontSize:25
            }

          }}

          />
          <Stack.Screen name="Home" component={Home}
          />

          </Stack.Navigator>

        </NavigationContainer>

      );
    };

    const Header =()=>{
      return(
        <TextInput placeholder='name' />
      )
    }
    export default App


