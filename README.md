# SIMPLE-AJA
AI
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List - Programmer's Helper</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 300px;
        }

        h1 {
            text-align: center;
            color: #333;
        }

        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        button {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        ul {
            list-style-type: none;
            padding: 0;
        }

        li {
            background-color: #f9f9f9;
            margin: 8px 0;
            padding: 10px;
            border-radius: 4px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        li.done {
            text-decoration: line-through;
            background-color: #e0e0e0;
        }

        .btn-remove {
            background-color: red;
            color: white;
            border: none;
            border-radius: 4px;
            padding: 5px;
            cursor: pointer;
        }

        .btn-remove:hover {
            background-color: darkred;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Masukkan tugas baru..." />
        <button onclick="addTask()">Tambah Tugas</button>
        <ul id="taskList"></ul>
    </div>

    <script>
        // Fungsi untuk menambahkan tugas baru
        function addTask() {
            const taskInput = document.getElementById("taskInput");
            const taskValue = taskInput.value.trim();

            if (taskValue === "") {
                alert("Tugas tidak boleh kosong!");
                return;
            }

            // Membuat elemen li baru untuk tugas
            const taskList = document.getElementById("taskList");
            const li = document.createElement("li");

            // Menambahkan teks tugas ke elemen li
            li.innerHTML = `${taskValue} 
                <button class="btn-remove" onclick="removeTask(this)">Hapus</button>
                <input type="checkbox" onclick="toggleDone(this)" />`;

            // Menambahkan elemen li ke daftar tugas
            taskList.appendChild(li);

            // Menghapus teks input setelah menambahkan tugas
            taskInput.value = "";
        }

        // Fungsi untuk menghapus tugas
        function removeTask(button) {
            const li = button.parentElement;
            li.remove();
        }

        // Fungsi untuk menandai tugas selesai
        function toggleDone(checkbox) {
            const li = checkbox.parentElement;
            if (checkbox.checked) {
                li.classList.add("done");
            } else {
                li.classList.remove("done");
            }
        }
    </script>
</body>
</html>
