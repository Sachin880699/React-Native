# Topic

1 ) The style for single screen <br>
2 ) Common style for all screen<br>
3 ) Change the title of the screen<br>



# code



    import React from 'react';
    import {Text,View, Button} from 'react-native';
    import {NavigationContainer} from "@react-navigation/native";
    import  {createNativeStackNavigator} from "@react-navigation/native-stack"

    const Stack = createNativeStackNavigator();

    const App = () => {
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


          />
          <Stack.Screen name="Home" component={Home}


          options={{
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

    const Login = (props)=>{
      return(
        <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
          <Text style={{fontSize:30}}>Login Screen</Text>
          <Button title="Go to Home Page" onPress={()=>props.navigation.navigate("Home")} />
        </View>
      )
    }
    export default App
