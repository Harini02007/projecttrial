<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Interview Questions Website</title>
  <link rel="stylesheet" href="style.css" />
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" />
</head>
<body>
  <div class="container">
    <h1 class="animate__animated animate__fadeInDown">💼 Interview Questions Hub</h1>

    <div class="categories animate__animated animate__fadeInLeft">
      <h2>Choose a Category:</h2>
      <select id="category-select" onchange="showQuestions()">
        <option value="">-- Select --</option>
        <option value="html">HTML/CSS</option>
        <option value="python">Python</option>
        <option value="java">Java</option>
        <option value="ds">Data Structures</option>
        <option value="aptitude">Aptitude</option>
        <option value="hr">HR</option>
        <option value="dbms">DBMS</option>
        <option value="wd">Web Development</option>
        <option value="networking">Networking</option>
        <option value="rdbms">RDBMS</option>
      </select>
    </div>

    <div id="questions-box" class="animate__animated animate__fadeInUp">
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
      <button onclick="startListening()" class="mic-btn">🎙 Speak Now</button>
      <p id="voice-output"></p>
    </div>
  </div>

  <script>
    const questions = {
      html: [
        "What is the difference between ID and Class in HTML?",
        "How does the box model work in CSS?",
        "What are semantic HTML tags?",
        "What is the use of z-index in CSS?",
        "Difference between inline and block elements."
      ],
      python: [
        "What are Python lists and tuples?",
        "Explain the concept of Python decorators.",
        "How is memory managed in Python?",
        "What is the difference between deep copy and shallow copy?",
        "What are *args and **kwargs in Python?"
      ],
      java: [
        "What is the difference between abstract class and interface?",
        "What is JVM, JRE, and JDK?",
        "Explain the concept of multithreading in Java.",
        "What is method overloading and overriding?",
        "Explain exception handling in Java."
      ],
      ds: [
        "What is the difference between Array and LinkedList?",
        "Explain Stack and Queue data structures.",
        "What is a binary search tree?",
        "What is a hash table?",
        "Explain Big-O notation with an example."
      ],
      aptitude: [
        "A man is twice as old as his son. Five years ago, he was three times as old. What is his current age?",
        "Solve: If 3x + 5 = 20, what is x?",
        "Find the next number in the series: 2, 6, 12, 20, ?",
        "If the cost price of 20 articles is equal to the selling price of 16 articles, find the gain %.",
        "A train running at 60 km/hr crosses a pole in 30 seconds. What is the length of the train?"
      ],
      hr: [
        "Tell me about yourself.",
        "What are your strengths and weaknesses?",
        "Where do you see yourself in 5 years?",
        "Why do you want to join our company?",
        "Describe a challenging situation and how you handled it.",
        "How do you handle stress and pressure?",
        "Are you willing to relocate or travel?",
        "What are your salary expectations?",
        "How do you handle criticism?",
        "What motivates you to do your best on the job?"
      ],
      dbms: [
        "What is normalization?",
        "Explain ACID properties in DBMS.",
        "What is the difference between primary key and unique key?",
        "What are joins? Explain different types.",
        "What is indexing in DBMS?"
      ],
      wd: [
        "What is responsive web design?",
        "Difference between frontend and backend development.",
        "What is REST API and how is it used in web development?",
        "What are some common web development frameworks?",
        "What is the role of HTTPS in websites?"
      ],
      networking: [
        "What is the OSI model?",
        "Explain difference between TCP and UDP.",
        "What is an IP address?",
        "What is DNS and how does it work?",
        "Explain the function of a router."
      ],
      rdbms: [
        "What is an RDBMS and how is it different from DBMS?",
        "Explain foreign key with example.",
        "What is SQL and its types?",
        "Explain the concept of transactions in RDBMS.",
        "What is a view and how is it used in RDBMS?"
      ]
    };

    function showQuestions() {
      const category = document.getElementById('category-select').value;
      const questionList = document.getElementById('question-list');
      questionList.innerHTML = '';
      if (category && questions[category]) {
        questions[category].forEach(q => {
          const li = document.createElement('li');
          li.textContent = q;
          questionList.appendChild(li);
        });
      }
    }

    function startListening() {
      const output = document.getElementById('voice-output');
      const recognition = new(window.SpeechRecognition || window.webkitSpeechRecognition)();
      recognition.lang = 'en-US';
      recognition.interimResults = false;
      recognition.maxAlternatives = 1;

      recognition.start();
      output.textContent = "Listening...";

      recognition.onresult = (event) => {
        const transcript = event.results[0][0].transcript;
        output.textContent = `You said: ${transcript}`;
      };

      recognition.onerror = (event) => {
        output.textContent = 'Error occurred in recognition: ' + event.error;
      };
    }
  </script>
</body>
</html>

   
