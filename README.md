
import './App.css';
import { useState, useEffect } from 'react';

const Person = (props) => {
  return(
    <>
    <h1>Name: {props.name}</h1>
    <h2>Last Name: {props.lastName}</h2>
    <h2>Age: {props.age}</h2>
    </>
  )
}

const App = () => {
  const [counter,setCounter] = useState(0);
  
  useEffect(() => {
    //alert("You've changed the counter to " + counter); ... [counter]
    setCounter(100);
  }, [])

  return (
    <div className="App">
      <Person name={'John'} lastName={'Doe'} age={25}/>
      <Person name='Andrew' lastName='Bonsted' age={19}/>
      <button onClick={() => setCounter((prevCount) => prevCount - 1)}>-</button>
      <h1>{counter}</h1>
      <button onClick={() => setCounter((prevCount) => prevCount + 1)}>+</button>
    </div>
  );
}

export default App;
