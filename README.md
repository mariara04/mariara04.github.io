<html>
    <head>
        <title>To-do List</title>
        <style>
            body {
              font-family: Arial, sans-serif;
              margin: 0;
              padding: 0;
              background: #f4f4f4;
              display: flex;
              justify-content: center;
              align-items: center;
              height: 100vh;
            }
            .container {
              background: white;
              padding: 20px;
              border-radius: 8px;
              box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
              width: 500px;
              text-align: center;
            }
            h1 {
              font-size: 24px;
              margin-bottom: 20px;
            }
            input {
              width: calc(100% - 20px);
              padding: 8px;
              margin-bottom: 10px;
              border: 1px solid #ddd;
              border-radius: 4px;
            }
            button {
              width: 100%;
              padding: 10px;
              background: #28a745;
              color: white;
              border: none;
              border-radius: 4px;
              cursor: pointer;
              font-size: 16px;
            }
            button:hover {
              background: #218838;
            }
            ul {
              list-style: none;
              padding: 0;
              margin: 0;
            }
            li {
              padding: 8px 10px;
              border: 1px solid #ddd;
              margin-bottom: 5px;
              border-radius: 4px;
              display: flex;
              justify-content: space-between;
              align-items:center
            }
            li span {
              flex-grow: 1;
              text-align: left;
            }
            li button {
              background: black;
              border: none;
              color: white;
              padding: 5px 10px;
              border-radius: 4px;
              cursor: pointer;
              width: 40%;
            }
            li button:hover {
              background: black;
            }
          </style>
        
    </head>
<body>
    <div class="container">
    <h1>To-Do List</h1>
    <input id="todo-input" type="text" placeholder="Add a new task">
    <button onclick="addTodo()">Add</button>
    <ul id="todo-list"></ul>
  </div>
  <script>
    function addTodo() {
      const input = document.getElementById('todo-input');
      const list = document.getElementById('todo-list');

      if (input.value.trim() !== "") {
        const listItem = document.createElement('li');
        const span = document.createElement('span');
        span.textContent = input.value;

        const deleteButton = document.createElement('button');
        deleteButton.textContent = "Delete";
        deleteButton.onclick = function() {
          list.removeChild(listItem);
        };

        listItem.appendChild(span);
        listItem.appendChild(deleteButton);
        list.appendChild(listItem);

        input.value = '';
      } else {
        alert("Please enter a task!");
      }
    }
  </script></body>
</html>
