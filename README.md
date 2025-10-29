# Ex06 BMI Calculator
## Date:29/10/25
## Name:Vimala Rani A

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
## App.jsx
```
import React, { useState } from "react";
import "./index.css";

function App() {
  const [weight, setWeight] = useState("");
  const [height, setHeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [status, setStatus] = useState("");

  const calculateBMI = () => {
    if (weight && height) {
      const heightInMeters = height / 100;
      const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);
      setBmi(bmiValue);

      if (bmiValue < 18.5) setStatus("Underweight 😔");
      else if (bmiValue < 24.9) setStatus("Normal Weight 😊");
      else if (bmiValue < 29.9) setStatus("Overweight 😐");
      else setStatus("Obese 😟");
    } else {
      alert("Please enter both weight and height!");
    }
  };

  const reset = () => {
    setWeight("");
    setHeight("");
    setBmi(null);
    setStatus("");
  };

  return (
    <div className="bmi-container">
      <h1>BMI Calculator</h1>

      <div className="input-section">
        <label>Weight (kg):</label>
        <input
          type="number"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
          placeholder="Enter weight"
        />

        <label>Height (cm):</label>
        <input
          type="number"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
          placeholder="Enter height"
        />

        <button onClick={calculateBMI}>Calculate</button>
        <button className="reset" onClick={reset}>Reset</button>
      </div>

      {bmi && (
        <div className="result-section">
          <h2>Your BMI: {bmi}</h2>
          <p>Status: <strong>{status}</strong></p>
        </div>
      )}
    </div>
  );
}

export default App;


```
##BMICalculator.jsx
```
import React, { useState } from "react";

function BMICalculator() {
  const [weight, setWeight] = useState("");
  const [height, setHeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState("");

  const calculateBMI = () => {
    if (weight > 0 && height > 0) {
      const heightInMeters = height / 100;
      const bmiValue = (weight / (heightInMeters ** 2)).toFixed(2);
      setBmi(bmiValue);

      if (bmiValue < 18.5) setMessage("You are underweight");
      else if (bmiValue < 24.9) setMessage("You have a normal weight");
      else if (bmiValue < 29.9) setMessage("You are overweight");
      else setMessage("You are obese");
    } else {
      alert("Please enter valid numbers for weight and height!");
    }
  };

  return (
    <div>
      <h1>BMI Calculator</h1>
      <input
        type="number"
        placeholder="Weight (kg)"
        value={weight}
        onChange={(e) => setWeight(e.target.value)}
      />
      <input
        type="number"
        placeholder="Height (cm)"
        value={height}
        onChange={(e) => setHeight(e.target.value)}
      />
      <button onClick={calculateBMI}>Calculate</button>

      {bmi && (
        <div>
          <h2>Your BMI: {bmi}</h2>
          <p>{message}</p>
        </div>
      )}
    </div>
  );
}

export default BMICalculator;


```
##index.js
```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./index.css";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);



```
## Home.jsx
```
import React from "react";

function Home() {
  return (
    <div>
      <h1>Welcome to the BMI Calculator</h1>
      <p>Click on "BMI Calculator" in the menu to start!</p>
    </div>
  );
}

export default Home;

```


## OUTPUT

<img width="1917" height="1078" alt="Screenshot 2025-10-29 102445" src="https://github.com/user-attachments/assets/4005e2d5-8532-4fea-a154-c07196a78839" />
<img width="1919" height="1079" alt="Screenshot 2025-10-29 102504" src="https://github.com/user-attachments/assets/76ec3a53-84d2-4247-80b7-f5f2d678645e" />


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
