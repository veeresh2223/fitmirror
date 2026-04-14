<!DOCTYPE html>
<html>
<head>
  <title>FitMirror</title>

  <!-- Font (STEP 2 already added) -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Poppins', sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #667eea, #764ba2);
      padding: 40px;
      color: white;
    }

    .box {
      background: white;
      color: black;
      padding: 25px;
      border-radius: 15px;
      animation: fadeIn 0.8s ease-in-out;
      width: 320px;
      margin: auto;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }

    button {
      background: #667eea;
      color: white;
      padding: 12px;
      border: none;
      margin-top: 10px;
      cursor: pointer;
      border-radius: 8px;
      width: 100%;
    }

    
    @keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

    select, input {
      padding: 10px;
      margin-top: 10px;
      width: 100%;
      border-radius: 8px;
    }

    #result {
      margin-top: 20px;
      font-weight: bold;
    }

    footer {
      margin-top: 20px;
      font-size: 12px;
    }
  </style>
</head>

<body>

  <div class="box">
    <h2>👕 FitMirror</h2>

    <input type="file"><br>

    <!-- Image preview -->
    <img id="preview" width="200" style="margin-top:10px; border-radius:10px;">

    <select id="occasion">
      <option>College</option>
      <option>Date</option>
      <option>Party</option>
    </select>

<button onclick="suggestOutfit()" id="btn">Suggest Outfit</button>
    <p id="result"></p>
  </div>

  <footer>Made by Veeresh 🚀</footer>

<script>

function suggestOutfit() {
  let btn = document.getElementById("btn");
  let result = document.getElementById("result");
  let occasion = document.getElementById("occasion").value;

  btn.innerText = "Thinking... 🤔";

  setTimeout(() => {
    let outfits = {
      College: [
        "😎 Oversized tee + Cargo pants + Sneakers",
        "👕 Shirt + Jeans + Watch",
      ],
      Date: [
        "🔥 White shirt + Black jeans + Perfume",
        "💙 Denim jacket + Tee + Clean shoes",
      ],
      Party: [
        "🖤 All black outfit + Chain",
        "✨ Shirt + Blazer + Boots",
      ]
    };

    let options = outfits[occasion];
    let random = Math.floor(Math.random() * options.length);

    result.innerText = options[random];
    btn.innerText = "Suggest Outfit";
  }, 1000);
}

</script>

</body>
</html>
