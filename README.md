<!DOCTYPE html>
<html>
<head>
  <title>FitMirror</title>

  <link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Poppins', sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #667eea, #764ba2);
      padding: 40px;
      color: white;
    }

    .hero {
      margin-bottom: 20px;
    }

    .box {
      background: white;
      color: black;
      padding: 25px;
      border-radius: 15px;
      width: 320px;
      margin: auto;
    }

    select, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      border-radius: 8px;
    }

    button {
      background: #667eea;
      color: white;
      border: none;
      cursor: pointer;
    }

    #result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <div class="hero">
    <h1>Style Yourself Smarter 👕</h1>
    <p>Your personal outfit assistant</p>
  </div>

  <div class="box">

    <select id="occasion">
      <option value="College">College 🎓</option>
      <option value="Date">Date ❤️</option>
      <option value="Party">Party 🎉</option>
    </select>

    <select id="style">
      <option value="Casual">Casual 😎</option>
      <option value="Attractive">Attractive 🔥</option>
      <option value="Smart">Smart 🧠</option>
      <option value="Minimal">Minimal 🖤</option>
    </select>

    <button id="btn" onclick="suggestOutfit()">Suggest Outfit</button>

    <p id="result"></p>
  </div>

  <script>
    function suggestOutfit() {
      let btn = document.getElementById("btn");
      let result = document.getElementById("result");

      let occasion = document.getElementById("occasion").value;
      let style = document.getElementById("style").value;

      btn.innerText = "Thinking... 🤔";

      setTimeout(() => {

        let outfits = {
          College: {
            Casual: ["👕 T-shirt + Jeans", "🧢 Hoodie + Joggers"],
            Attractive: ["🔥 Fitted shirt + Dark jeans"],
            Smart: ["👔 Shirt + Formal pants"],
            Minimal: ["🖤 Plain tee + Black jeans"]
          },
          Date: {
            Casual: ["👕 Tee + Jeans"],
            Attractive: ["🔥 White shirt + Black jeans"],
            Smart: ["👔 Shirt + Blazer"],
            Minimal: ["🖤 All black outfit"]
          },
          Party: {
            Casual: ["👕 Printed tee"],
            Attractive: ["🔥 Shirt + Chain"],
            Smart: ["👔 Blazer + Watch"],
            Minimal: ["🖤 Black outfit"]
          }
        };

        let options = outfits[occasion][style];

        let random = Math.floor(Math.random() * options.length);

        result.innerText = options[random];

        btn.innerText = "Suggest Outfit";

      }, 1000);
    }
  </script>

</body>
</html>
