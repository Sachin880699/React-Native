# Topic

1 ) Make a function for the API call<br>
2 ) Store API data in the state<br>
3 ) Display API data<br>


# Basic get API call

    import React, {useEffect , useState} from 'react';
    import {Text,View, Button, TextInput} from 'react-native';



    const App = () => {

      const [data , setData] = useState(undefined);

    const getAPIData= async ()=>{
      //API call
      const url = "https://jsonplaceholder.typicode.com/posts/1";
      let result = await fetch(url);
      result = await result.json();
      setData(result)
    }

    useEffect(()=>{
      getAPIData();

    },[])

     return(
      <View>
        <Text style={{fontSize:30}}>API Call</Text>
      {
        data? <View>
        <Text style={{fontSize:30}}>ID: {data.id}</Text>
        <Text style={{fontSize:30}}>UserId: {data.userId}</Text>
        <Text style={{fontSize:30}}>Title : {data.title}</Text>
        <Text style={{fontSize:30}}>Body : {data.body}</Text>

        </View>:null
      }
      </View>


      );
    };
    export default App
