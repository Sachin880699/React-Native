


    import { text } from 'express';
    import React, { useState } from 'react';
    import { Image, RefreshControl, ScrollView, Text, View, StyleSheet, TextInput, Button } from 'react-native';


    const logo = {
        uri: 'https://reactnative.dev/img/tiny_logo.png',
        width: 64,
        height: 64
    };


    const ContactYoutube = () => {
        const [email, Setemail] = useState("")
        const [password, Setpassword] = useState("")
        const [color, changeColor] = useState('red');
        const [refreshing, setRefreshing] = React.useState(false);

        function check_logi() {
            if (email == "sachin" && password == "sachin") {
                alert("Yes")
            }
            else {
                alert("Sorry password is worng")
            }
        }

        const onRefresh = () => {
            setRefreshing(true);
            setTimeout(() => {
                changeColor('green');
                setRefreshing(false);
            }, 2000);
        };


        return (
            <ScrollView
                refreshControl={
                    <RefreshControl refreshing={refreshing}
                        onRefresh={onRefresh} />
                }
            >


                <Image source={logo} style={styles.logo} />

                <Text style={{ marginTop: 50, marginLeft: 140 }}>Enter Email</Text>
                <TextInput
                    style={{ height: 40, width: "55%", marginLeft: 90, borderColor: 'gray', borderWidth: 1, marginBottom: 20 }}

                    placeholder="Enter Your Email"

                    underlineColorAndroid="transparent"
                    onChangeText={(email) => Setemail(email)}
                    value={email}
                />

                <Text style={{ marginTop: 50, marginLeft: 140 }}>Enter Password</Text>
                <TextInput
                    style={{ height: 40, width: "55%", marginLeft: 90, borderColor: 'gray', borderWidth: 1, marginBottom: 20 }}

                    placeholder="Enter Your Password"

                    underlineColorAndroid="transparent"

                    onChangeText={(password) => Setpassword(password)}
                    value={password}

                />
                <View style={[{ width: "40%", marginLeft: 120, margin: 10, backgroundColor: "red" }]}>
                    <Button title='login' onPress={check_logi} />
                </View>
            </ScrollView>
        );
    }

    const styles = StyleSheet.create({
        logo: {
            width: 200,
            height: 200,
            marginLeft: 80,
            marginTop: 70
        },
    })

    export default ContactYoutube;
