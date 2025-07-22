<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Interview Questions Website</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>💼 Interview Questions Hub</h1>

    <div class="categories">
      <h2>Choose a Category:</h2>
      <select id="category-select" onchange="showQuestions()">
        <option value="">-- Select --</option>
        <option value="html">HTML/CSS</option>
        <option value="python">Python</option>
        <option value="java">Java</option>
        <option value="ds">Data Structures</option>
        <option value="aptitude">Aptitude</option>
      </select>
    </div>

    <div id="questions-box">
      <h2>Questions:</h2>
      <ul id="question-list"></ul>
    </div>

    <div class="features">
      <h2>🧠 Problem Solving Video</h2>
      <video controls width="100%">
        <source src="videos/problem-solving.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>

      <h2>🎤 Voice to Text (Speech Input)</h2>
      <button onclick="startListening()">🎙 Speak Now</button>
      <p id="voice-output"></p>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
