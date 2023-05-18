# Topic

1 ) Install the NPM top Tab package. <br>
2 ) Update Code for Navigation<br>

npm start --clean-cache


npm install @react-navigation/material-top-tabs react-native-tab-view

npm install react-native-pager-view


# code 




    import React from 'react';
    import {Text,View, Button, TextInput} from 'react-native';
    import {NavigationContainer} from "@react-navigation/native"
    import {createBottomTabNavigator} from "@react-navigation/bottom-tabs"

    import {createMaterialTopTabNavigator} from "@react-navigation/material-top-tabs"

    const Tab = createMaterialTopTabNavigator()


    const App = () => {

     return(
        <NavigationContainer>
          <Tab.Navigator>
            <Tab.Screen name="Login" component={Login} />
            <Tab.Screen name="Signup" component={SignUp} />
            <Tab.Screen name="Other" component={Other} />
          </Tab.Navigator>
        </NavigationContainer>

      );
    };

    const Login=()=>{
      return <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
        <Text style={{fontSize:40}}>Login</Text>
      </View>
    }

    const SignUp=()=>{
      return <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
        <Text style={{fontSize:40}}>SignUp</Text>
      </View>
    }
    const Other=()=>{
      return <View style={{flex:1,justifyContent:"center",alignItems:"center"}}>
        <Text style={{fontSize:40}}>Other</Text>
      </View>
    }

    export default App
