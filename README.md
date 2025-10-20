<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f7f9;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .container {
      background: #fff;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      width: 350px;
    }

    h2 {
      text-align: center;
      color: #333;
    }

    input[type="text"] {
      width: 80%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      margin-right: 5px;
    }

    button {
      padding: 10px;
      border: none;
      background-color: #007bff;
      color: white;
      border-radius: 8px;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }

    li {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #f0f2f5;
      padding: 10px;
      border-radius: 8px;
      margin-bottom: 10px;
    }

    li.completed span {
      text-decoration: line-through;
      color: gray;
    }

    .delete-btn {
      background: red;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      padding: 6px;
    }

    .delete-btn:hover {
      background: darkred;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>📝 To-Do List</h2>
    <div>
      <input type="text" id="taskInput" placeholder="Enter a task...">
      <button onclick="addTask()">Add</button>
    </div>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById('taskInput');
      const taskText = input.value.trim();
      if (taskText === '') return alert('Please enter a task!');
      
      const li = document.createElement('li');
      const span = document.createElement('span');
      span.textContent = taskText;
      span.onclick = () => li.classList.toggle('completed');

      const delBtn = document.createElement('button');
      delBtn.textContent = 'X';
      delBtn.className = 'delete-btn';
      delBtn.onclick = () => li.remove();

      li.appendChild(span);
      li.appendChild(delBtn);
      document.getElementById('taskList').appendChild(li);

      input.value = '';
    }
  </script>
</body>
</html>
