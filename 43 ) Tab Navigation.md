
# Topics

1 ) install npm tab package <br>
2 ) make 2 component for the screen <br>
3 ) Make tab navigation wrapper<br>
4 ) Interviewq Question<br>

5 ) npm start --clean-cache

CMD ) npm install @react-navigation/bottom-tabs


# code 




    import React from 'react';
    import {Text,View, Button, TextInput} from 'react-native';
    import {NavigationContainer} from "@react-navigation/native"
    import {createBottomTabNavigator} from "@react-navigation/bottom-tabs"


    const Tab = createBottomTabNavigator()


    const App = () => {

     return(
        <NavigationContainer>
          <Tab.Navigator>
            <Tab.Screen name="Login" component={Login} />
            <Tab.Screen name="Signup" component={SignUp} />
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


    export default App

