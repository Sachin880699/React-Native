1 ) What are components ?
2 ) Example of Component
3 ) Interview question


# components in react native

1 ) Independent and resuable code such as functioin
2 ) tow type of components<br/>

<b>Functional</b>

<b>class-based</b>



# create multiple components in single file


    import React from 'react';
    import { Button, Text, View } from 'react-native'

    function fruit(){
      return 'apple'
    }
    const App = () => {
      return (
        <View>
          <Text style={{ fontSize: 30 }}>My Name Is : Components</Text>
          <UserData/>
          <CompanyData/>

        </View>
      );
    };

    const UserData = () => {

      return(
        <Text style={{fontSize:20}}>Hello</Text>
      )
    }

    const CompanyData = () => {

      return(
        <Text style={{fontSize:20}}>Company Data</Text>
      )
    }

    export default App
    
# create component in seprate file


<b> 1 App.js </b>

    import React from 'react';
    import { Button, Text, View } from 'react-native'
    import CompanyData from './components/CompanyData';

    function fruit(){
      return 'apple'
    }
    const App = () => {
      return (
        <View>
          <Text style={{ fontSize: 30 }}>My Name Is : Components</Text>
          <UserData/>
          <CompanyData/>

        </View>
      );
    };
    const UserData = () => {
      return(
        <Text style={{fontSize:20}}>Hello</Text>
      )
    }
    export default App
    
    
 

<b>2 ) now create a components folder inside that folder create ( CompanyData.js ) file </b>


    import {Text , View} from 'react-native'

    const CompanyData = () => {

        return(
          <Text style={{fontSize:20}}>Company Data</Text>
        )
      }

      export default CompanyData



# interveiw question

1 ) can we create nedsted component
Ans : Yes

2 ) diff between function component and calss component


