<script>
    let displayValue = "0";
    let expression = "";
  
    function handleButtonClick(event) {
      const buttonValue = event.target.innerText;
      if (displayValue === "0") {
        displayValue = buttonValue;
        expression += buttonValue;
      } else {
        displayValue += buttonValue;
        expression += buttonValue;
      }
    }
  
    function handleClear() {
      displayValue = "0";
      expression = "";
    }
  
    function handleCalculate() {
      try {
        displayValue = eval(expression);
        expression = "";
      } catch (error) {
        displayValue = "Error";
        expression = "";
      }
    }
  </script>
  
  <div class="calculator">
    <div class="display">
      <input type="text" bind:value={displayValue} readonly />
    </div>
    <div class="buttons">
      <button class="clear" on:click={handleClear}>AC</button>
      <button on:click={handleButtonClick}>1</button>
      <button on:click={handleButtonClick}>2</button>
      <button on:click={handleButtonClick}>3</button>
      <button on:click={handleButtonClick}>4</button>
      <button on:click={handleButtonClick}>5</button>
      <button on:click={handleButtonClick}>6</button>
      <button on:click={handleButtonClick}>7</button>
      <button on:click={handleButtonClick}>8</button>
      <button on:click={handleButtonClick}>9</button>
      <button on:click={handleButtonClick}>+</button>
      <button on:click={handleButtonClick}>-</button>
      <button on:click={handleButtonClick}>/</button>
      <button on:click={handleButtonClick}>*</button>
      <button on:click={handleButtonClick}>.</button>
      <button class="equal" on:click={handleCalculate}>=</button>
      <button on:click={handleButtonClick}>-</button>
    </div>
  </div>
  
  <style>
    .calculator {
      width: 250px;
      margin: 0 auto;
      background-color: #282a36;
      border-radius: 10px;
      padding: 20px;
    }
  
    .display {
      margin-bottom: 20px;
    }
  
    input {
      width: 100%;
      height: 40px;
      padding: 0.5rem;
      font-size: 1.5rem;
      text-align: right;
      border: none;
      border-radius: 5px;
      background-color: #44475a;
      color: #f8f8f2;
    }
  
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
  
    button {
      width: 100%;
      height: 40px;
      font-size: 1.5rem;
      border: none;
      border-radius: 5px;
      background-color: #6272a4;
      color: #f8f8f2;
      cursor: pointer;
      transition: background-color 0.2s ease-in-out;
    }
  
    button:hover {
      background-color: #bd93f9;
    }
  
    .clear {
      grid-column: span 2;
      background-color: #ff5555;
    }
  
    .equal {
      background-color: #50fa7b;
    }
  </style>