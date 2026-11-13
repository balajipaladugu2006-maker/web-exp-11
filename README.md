# Exp 11 – Basic Calculator using React
## NAME: Paladugu Venkata Balaji
## REG NO: 2305001024
## Aim
To develop a basic calculator application using React that performs arithmetic operations such as addition, subtraction, multiplication, and division.

## Objectives
1. To understand React components and JSX.
2. To use the useState() hook to manage calculator values.
3. To handle user input using onChange events.
4. To perform arithmetic operations using conditional statements.
5. To implement Calculate and Clear buttons using event handling.
# Program
## App.jsx
~~~python 
import { useState } from "react";
import "./App.css";

function App() {
  const [num1, setNum1] = useState("");
  const [num2, setNum2] = useState("");
  const [operator, setOperator] = useState("+");
  const [result, setResult] = useState("");

  const calculate = () => {
    const a = Number(num1);
    const b = Number(num2);
    let answer;

    if (num1 === "" || num2 === "") {
      setResult("Please enter both numbers");
      return;
    }

    if (operator === "+") {
      answer = a + b;
    } else if (operator === "-") {
      answer = a - b;
    } else if (operator === "*") {
      answer = a * b;
    } else if (operator === "/") {
      answer = b !== 0 ? a / b : "Cannot divide by zero";
    }

    setResult(answer);
  };

  const clearCalculator = () => {
    setNum1("");
    setNum2("");
    setOperator("+");
    setResult("");
  };

  return (
    <div>
      <h1>Basic Calculator</h1>

      <input
        type="number"
        placeholder="Enter first number"
        value={num1}
        onChange={(e) => setNum1(e.target.value)}
      />

      <br /><br />

      <select
        value={operator}
        onChange={(e) => setOperator(e.target.value)}
      >
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>

      <br /><br />

      <input
        type="number"
        placeholder="Enter second number"
        value={num2}
        onChange={(e) => setNum2(e.target.value)}
      />

      <br /><br />

      <button onClick={calculate}>Calculate</button>
      <button onClick={clearCalculator}>Clear</button>

      <h2>Result: {result}</h2>
    </div>
  );
}

export default App;
~~~ 
## App.css
~~~
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(135deg, #667eea, #764ba2);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  background: #ffffff;
  padding: 35px;
  width: 350px;
  border-radius: 20px;
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.25);
  text-align: center;
}

h1 {
  color: #333;
  margin-bottom: 25px;
  font-size: 28px;
}

input {
  width: 100%;
  padding: 13px;
  margin: 10px 0;
  border: 2px solid #ddd;
  border-radius: 10px;
  font-size: 16px;
  outline: none;
  transition: 0.3s;
}

input:focus {
  border-color: #667eea;
  box-shadow: 0 0 8px rgba(102, 126, 234, 0.3);
}

.buttons {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
  margin-top: 20px;
}

button {
  padding: 13px;
  border: none;
  border-radius: 10px;
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 15px rgba(102, 126, 234, 0.4);
}

button:active {
  transform: scale(0.95);
}

h2 {
  margin-top: 25px;
  color: #333;
  font-size: 22px;
  background: #f1f3ff;
  padding: 12px;
  border-radius: 10px;
}
~~~
## Output
<img width="1047" height="562" alt="image" src="https://github.com/user-attachments/assets/bbfc95c6-5256-402d-b433-22194e0561d5" />
<img width="1042" height="547" alt="image" src="https://github.com/user-attachments/assets/88ca84bf-5116-4e76-b265-15767dcfc25e" />


## Result
Thus, a basic calculator application was successfully implemented using React with useState(), event handling, and conditional statements to perform arithmetic operations.
