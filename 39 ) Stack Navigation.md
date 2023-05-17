
# Topics

1 ) Install react navigation
2 ) Install Dependencies.
3 ) Make wrapper of navigation
4 ) Make Login and Home componnet
5 ) Navigate between screens



# Package Install

1 ) npm install @react-navigation/native <br>
2 ) npx expo install react-native-screens react-native-safe-area-context <br>
3 ) npm install @react-navigation/native-stack



# Code



    import React from 'react';
    import {Text,View, Button} from 'react-native';
    import {NavigationContainer} from "@react-navigation/native";
    import  {createNativeStackNavigator} from "@react-navigation/native-stack"

    const Stack = createNativeStackNavigator();

    const App = () => {
      return(
        <NavigationContainer>
          <Stack.Navigator>

          <Stack.Screen name="Login" component={Login} />
          <Stack.Screen name="Home" component={Home} />

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
