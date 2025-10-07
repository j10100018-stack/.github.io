<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <title>簡易計算機</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f7f7f7;
      text-align: center;
      padding: 50px;
    }
    .calculator {
      background-color: white;
      border-radius: 8px;
      padding: 20px;
      display: inline-block;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input[type="number"] {
      width: 100px;
      padding: 5px;
      margin: 10px;
    }
    select, button {
      padding: 5px 10px;
      margin: 10px;
    }
    #result {
      margin-top: 20px;
      font-size: 1.2em;
      color: #333;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <h2>簡易計算機</h2>
    <input type="number" id="num1" placeholder="數字1">
    <br>
    <input type="number" id="num2" placeholder="數字2">
    <br>
    <select id="operator">
      <option value="+">加 (+)</option>
      <option value="-">減 (-)</option>
      <option value="*">乘 (*)</option>
      <option value="/">除 (/)</option>
    </select>
    <br>
    <button onclick="calculate()">計算</button>
    <div id="result"></div>
  </div>

  <script>
    function calculate() {
      const num1 = parseFloat(document.getElementById('num1').value);
      const num2 = parseFloat(document.getElementById('num2').value);
      const operator = document.getElementById('operator').value;
      let result;

      if (isNaN(num1) || isNaN(num2)) {
        result = "請輸入兩個有效的數字。";
      } else {
        switch (operator) {
          case '+':
            result = num1 + num2;
            break;
          case '-':
            result = num1 - num2;
            break;
          case '*':
            result = num1 * num2;
            break;
          case '/':
            if (num2 === 0) {
              result = "無法除以 0";
            } else {
              result = num1 / num2;
            }
            break;
          default:
            result = "未知的運算符號";
        }
      }

      document.getElementById('result').innerText = "結果: " + result;
    }
  </script>
</body>
</html>
