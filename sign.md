

#  App.js 

          import React from 'react';
          import {Text , View, StyleSheet , SafeAreaView} from 'react-native';
          import SignInScreen from './src/screens/SigninScreen/SignInScreen';


          const App = () => {
            return (
              <SafeAreaView style={styles.root}>
                <SignInScreen />
              </SafeAreaView>
            );
          }

          const styles = StyleSheet.create({
            root:{
              flex:1,
              backgroundColor:"#F9FBFC"
            }
          })

          export default App;


# ________ src/components/CustomInput.js


          import React from 'react';
          import {Text , TextInput, View, StyleSheet} from 'react-native';

          const CustomInput = ({value,setValue , placeholder , secureTextEntry}) => {
              return (
                  <View style={styles.container}>
                      <TextInput
                      value = {value}
                      placeholder={placeholder}
                      onChangeText = {setValue}
                      style={styles.input}
                      secureTextEntry={secureTextEntry}
                      />

                  </View>
              );
          }

          const styles = StyleSheet.create({

              container:{
                  backgroundColor:"white",
                  width:"100%",
                  borderColor:"black",
                  borderWidth:1,
                  borderRadius:6,

                  paddingHorizontal:10,
                  marginVertical:6,

              },
              input:{
                  color:"black"
              }

          })

          export default CustomInput;
          
 
# ________ src/components/index.js


        export {default} from "./SignInScreen";


# __________ src/screens/SignInScreen/SignInScreen.js



        import React , {useState} from 'react';
        import {Text ,  View, StyleSheet , Image, useWindowDimensions , ScrollView} from 'react-native';
        import Logo from "../../../assets/images/Logo.png"
        import CustomInput from '../../components/CustomInput';
        import CustomButton from '../../components/CustomButton/CustomButton';
        const SignInScreen = () => {;
            const {height} = useWindowDimensions()
            const [username , setUsername] = useState("");
            const [password , setPassword] = useState("")

            const onSignInPressed = () =>{
                console.warn("sachin")
            }

            const onForgotPasswordPress = () =>{
                console.warn("forgot password")
            }
            const onSignInFacebook = () =>{
                console.warn("Facebook Signup")
            }
            const onSignInGoogle = () =>{
                console.warn("Google Login")
            }
            const onSignUpPress = () =>{
                console.warn("signup")
            }
            return (
                <View style={styles.root}>
                    <Image source={Logo} style={styles.logo} />


                    <CustomInput placeholder="Username" value={username} setValue={setUsername} />
                    <CustomInput placeholder="password" secureTextEntry={true} value = {password} setValue = {setPassword} />

                    <CustomButton text = "Sign In" onPress={onSignInPressed} />

                    <CustomButton text = "Forgot Password" onPress={onForgotPasswordPress}
                    type="TERTIARY"
                    />

        <CustomButton text = "Sign In With Facebook" onPress={onSignInFacebook}
        bgColor="#E7EFAF4"
        fgColor="#4765A9"
        />
        <CustomButton text = "Sign In With Google" onPress={onSignInGoogle}
        bgColor="#FAE9EA"
        fgColor="#DD444"
        />
        <CustomButton text = "Don't have an account ? Create one" onPress={onSignUpPress}
        bgColor="#FAE9EA"
        fgColor="black"
        />
                </View>
            );
        }
        const styles = StyleSheet.create({
            logo:{
                width:400,
                height:100
            },
            root:{
                alignItems:"center",
                padding:20,

            }
        })
        export default SignInScreen;
        


# __________ src/screens/SignInScreen/index.js

      export {default} from "./SignInScreen";
      
      

# __________ src/components/CustomButton/CustomButton.js


        import React from 'react';
        import {View, StyleSheet , Text , Pressable , type} from 'react-native';

        const CustomButton = ({onPress , text , type="PRIMARY" , bgColor , fgColor}) => {
            return (
                <Pressable onPress={onPress} style={[styles.container, styles[`container_${type}`],
                bgColor ? {backgroundColor:bgColor}:{}]}>
                    <Text style={[styles.text , styles[`text_${type}`],
                    fgColor ? {color: fgColor}: {},
                ]}>{text}</Text>
                </Pressable>
            );
        }

        const styles = StyleSheet.create({
        container:{
            backgroundColor:"#3B71F3",
            width:"100%",
            marginVertical:5,
            alignItems:"center",
            borderRadius:5,
            height:"8%"

        },
        container_PRIMARY:{
            backgroundColor:"#3B71F3",

        },
        container_TERTIARY:{
            backgroundColor:"white"
        },
        text: {
            fontWeight:"bold",
            color:"white",
            marginTop:"2%"

        },
        text_TERTIARY:{
            color:"gray"
        }

        })

        export default CustomButton;
        
        
        

# __________ src/components/CustomButton/index.js
        
        export {default} from "./CustomButton";
 



