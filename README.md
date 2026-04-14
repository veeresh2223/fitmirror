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
      margin-top: 20px;
      transition: 0.3s;
      .box:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.3);
}
      background: white;
      color: black;
      padding: 25px;
      border-radius: 15px;
      animation: fadeIn 0.8s ease-in-out;
      width: 320px;
      margin: auto;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);

      .hero {
  margin-bottom: 30px;
}

.hero h1 {
  font-size: 32px;
  margin-bottom: 5px;
}

.hero p {
  font-size: 14px;
  opacity: 0.9;
}
    }

    button {
      transform :scale(0.95);
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
  opacity: 0;
  transform: translateY(10px);
  transition: all 0.4s ease;
}

    footer {
      margin-top: 20px;
      font-size: 12px;
    }
  </style>
</head>

<body>
<div class="hero">
  <h1>Style Yourself Smarter 👕</h1>
  <p>Your personal outfit assistant powered by smart suggestions</p>
</div>

  <div class="box">
    <h2>👕 FitMirror</h2>

    <input type="file"><br>

<img id="preview" width="200" style="margin-top:10px; border-radius:10px;">

<!-- Occasion -->
<select id="occasion">
  <option>College</option>
  <option>Date</option>
  <option>Party</option>
</select>

<!-- Style -->
<select id="style">
  <option>Casual 😎</option>
  <option>Attractive 🔥</option>
  <option>Smart 🧠</option>
  <option>Minimal 🖤</option>
</select>
      <option>College</option>
      <option>Date</option>
      <option>Party</option>
    </select>

<button onclick="suggestOutfit()" id="btn">Suggest Outfit</button>
    <p id="result"></p>
  </div>

<footer>
  Made by Veeresh 🚀 <br>
  <small>FitMirror © 2026</small>
</footer>
<script>
function suggestOutfit() {
  let btn = document.getElementById("btn");
  let result = document.getElementById("result");
  let occasion = document.getElementById("occasion").value;
  let style = document.getElementById("style").value;

  btn.innerText = "Thinking... 🤔";

  setTimeout(() => {

    // 👇 STEP 4 CODE GOES HERE
    let outfits = {
      College: {
        "Casual 😎": ["👕 Oversized tee + Jeans + Sneakers"],
        "Attractive 🔥": ["🔥 Fitted shirt + Dark jeans"],
        "Smart 🧠": ["👔 Shirt + Formal pants"],
        "Minimal 🖤": ["🖤 Plain tee + Black jeans"]
      },
      Date: {
        "Casual 😎": ["👕 Tee + Jeans"],
        "Attractive 🔥": ["🔥 White shirt + Black jeans"],
        "Smart 🧠": ["👔 Shirt + Blazer"],
        "Minimal 🖤": ["🖤 All black outfit"]
      },
      Party: {
        "Casual 😎": ["👕 Printed tee"],
        "Attractive 🔥": ["🔥 Shirt + Chain"],
        "Smart 🧠": ["👔 Blazer + Watch"],
        "Minimal 🖤": ["🖤 Black outfit"]
      }
    };

    // 👇 THIS LINE USES IT
    let style = document.getElementById("style").value;trim();
    let random = Math.floor(Math.random() * options.length);

    result.innerText = options[random];
    btn.innerText = "Suggest Outfit";

  }, 1000);
}
  let style = document.getElementById("style").value;

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

   let options = outfits[occasion][style];

if (!options) {
  result.innerText = "⚠️ Try selecting options again";
  btn.innerText = "Suggest Outfit";
  return;
}
    let random = Math.floor(Math.random() * options.length);

    result.style.opacity = 0;
result.style.transform = "translateY(10px)";

setTimeout(() => {
  result.innerText = options[random];
  result.style.opacity = 1;
  result.style.transform = "translateY(0)";
}, 200);
    btn.innerText = "Suggest Outfit";
  }, 1000);
}

</script>

</body>
</html>
