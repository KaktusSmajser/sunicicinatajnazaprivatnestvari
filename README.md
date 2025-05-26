# sunicicinatajnazaprivatnestvari
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sunčica's Birthday Invitation</title>
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #f6d365 0%, #fda085 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 2rem;
    }
    .container {
      background: #fff;
      padding: 2rem;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      max-width: 600px;
      width: 100%;
      text-align: center;
    }
    h1 {
      font-family: 'Pacifico', cursive;
      font-size: 2.5rem;
      color: #ff4e9b;
      margin-bottom: 1rem;
    }
    label, p {
      font-size: 1rem;
      margin: 0.5rem 0;
    }
    input[type="text"], select {
      padding: 0.5rem;
      width: 100%;
      border-radius: 10px;
      border: 1px solid #ccc;
      margin-bottom: 1rem;
    }
    button {
      background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
      color: white;
      border: none;
      padding: 0.75rem 2rem;
      border-radius: 50px;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s;
    }
    button:hover {
      background: linear-gradient(135deg, #c471f5 0%, #fa71cd 100%);
    }
    .hidden {
      display: none;
    }
    #invitation-card {
      margin-top: 2rem;
    }
    #invitation-card img {
      max-width: 200px;
      border-radius: 15px;
      margin-bottom: 1rem;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Sunčica's Birthday!</h1>
    <div id="name-form">
      <label for="nameInput">Enter your name:</label>
      <input type="text" id="nameInput" placeholder="Your name">
      <button onclick="startPoll()">Start</button>
    </div>

    <form id="poll-form" class="hidden" onsubmit="handlePollSubmit(event)">
      <p>1. Što želite piti na rođendanu?</p>
      <input type="text" name="drink">

      <p>2. Voćna ili čokoladna torta?</p>
      <input type="text" name="cake">

      <p>3. Dali želite da se slikamo?</p>
      <input type="text" name="photos">

      <p>4. Želite li dress code?</p>
      <input type="text" name="dresscode">

      <button type="submit">Submit Answers</button>
    </form>

    <div id="invitation-card" class="hidden">
      <img id="friend-image" src="" alt="Friend Image">
      <h2>You're Invited, <span id="friend-name"></span>!</h2>
      <p><strong>Date:</strong> 6.6.2025</p>
      <p><strong>Time:</strong> 21:00</p>
      <p><strong>Location:</strong> Moja kuća</p>
      <p>We can't wait to celebrate with you! 🎉</p>
    </div>
  </div>

  <script>
    const nameToImage = {
      "Pata": "https://i.ibb.co/TDw2z6Sj/Pata.jpg" ,
      "Matej": "https://example.com/matej.jpg",
      "Laura": "https://example.com/laura.jpg",
      "Hanči": "https://example.com/hanci.jpg",
      "Lara": "https://example.com/lara.jpg",
      "Hriss": "https://example.com/hriss.jpg",
      "Lamija": "https://example.com/lamija.jpg",
      "Čok": "https://example.com/cok.jpg",
      "Ivo": "https://example.com/ivo.jpg",
      "Mato": "https://example.com/mato.jpg",
      "Joško": "https://example.com/josko.jpg",
      "Tea": "https://example.com/tea.jpg",
      "Karla": "https://example.com/karla.jpg"
    };

    let currentName = "";

    function startPoll() {
      const nameInput = document.getElementById('nameInput').value.trim();
      if (!nameInput) return alert("Please enter your name!");
      currentName = nameInput;
      document.getElementById('name-form').classList.add('hidden');
      document.getElementById('poll-form').classList.remove('hidden');
    }

    function handlePollSubmit(event) {
      event.preventDefault();
      document.getElementById('poll-form').classList.add('hidden');
      const imgUrl = nameToImage[currentName] || "https://via.placeholder.com/200";

      document.getElementById('friend-image').src = imgUrl;
      document.getElementById('friend-name').textContent = currentName;
      document.getElementById('invitation-card').classList.remove('hidden');
    }
  </script>
</body>
</html>
