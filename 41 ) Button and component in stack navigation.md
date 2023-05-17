# Topic

1 ) Add a Button in the Navigation<br>
2 ) Action on the navigation button<br>
3 ) add component in navigation<br>



# App.js


    import React from 'react';
    import {Text,View, Button, TextInput} from 'react-native';
    import {NavigationContainer} from "@react-navigation/native";
    import  {createNativeStackNavigator} from "@react-navigation/native-stack"
    import { Login } from './components/Login';

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

    const Home = ()=>{
      return(
        <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
          <Text style={{fontSize:30}}>Home Screen</Text>
        </View>
      )
    }



    const Header =()=>{
      return(
        <TextInput placeholder='name' />
      )
    }
    export default App
    
# Login.js


    import {Text,View, Button, TextInput} from 'react-native';

    export const Login = (props)=>{
        return(
          <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
            <Text style={{fontSize:30}}>Login Screen</Text>
            <Button title="Go to Home Page" onPress={()=>props.navigation.navigate("Home")} />
          </View>
        )
      }



