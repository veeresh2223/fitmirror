<!DOCTYPE html>
<html>
<head>
  <title>FitMirror</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      background: #f5f5f5;
      padding: 40px;
    }

    .box {
      background: white;
      padding: 20px;
      border-radius: 10px;
      width: 300px;
      margin: auto;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    button {
      background: black;
      color: white;
      padding: 10px;
      border: none;
      margin-top: 10px;
      cursor: pointer;
      border-radius: 5px;
    }

    select, input {
      padding: 8px;
      margin-top: 10px;
      width: 100%;
    }

    #result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <div class="box">
    <h2>👕 FitMirror</h2>

    <input type="file"><br>

    <select id="occasion">
      <option>College</option>
      <option>Date</option>
      <option>Party</option>
    </select>

    <button onclick="suggestOutfit()">Suggest Outfit</button>

    <p id="result"></p>
  </div>

  <script>
    function suggestOutfit() {
      let occasion = document.getElementById("occasion").value;
      let result = document.getElementById("result");

      if (occasion === "College") {
        result.innerText = "👕 Jeans + T-shirt + Sneakers 😎";
      } else if (occasion === "Date") {
        result.innerText = "🔥 White shirt + Black jeans + Watch";
      } else {
        result.innerText = "🖤 All black outfit + Stylish shoes";
      }
    }
  </script>

</body>
</html>
