<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manajemen Acara</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        #login-form, #calendar {
            display: none;
            background: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        #login-form input {
            margin: 10px 0;
            padding: 10px;
            width: calc(100% - 22px);
        }
        #calendar {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>

<header>
    <h1>Manajemen Acara</h1>
    <img id="logo" src="your-logo.png" alt="Logo" style="width: 150px;">
</header>

<div class="container">
    <div id="login-form">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username" required>
        <input type="password" id="password" placeholder="Sandi" required>
        <button onclick="login()">Masuk</button>
    </div>

    <div id="calendar">
        <h2>Kalender Acara</h2>
        <div id="calendar-view"></div>
        <table>
            <thead>
                <tr>
                    <th>Tanggal</th>
                    <th>Acara</th>
                    <th>Lokasi</th>
                </tr>
            </thead>
            <tbody id="event-table">
                <!-- Data acara akan ditambahkan di sini -->
            </tbody>
        </table>
    </div>
</div>

<script>
    function login() {
        const username = document.getElementById('username').value;
        const password = document.getElementById('password').value;

        if (username === 'alfamusic01' && password === '99') {
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('calendar').style.display = 'block';
            loadCalendar();
        } else {
            alert('Username atau sandi salah.');
        }
    }

    function loadCalendar() {
        // Placeholder untuk kalender interaktif
        document.getElementById('calendar-view').innerHTML = '<p>Kalender interaktif akan ditampilkan di sini.</p>';
        addEvent('2023-12-06', 'Rapat Tim', 'Ruang Rapat 1');
    }

    function addEvent(date, event, location) {
        const table = document.getElementById('event-table');
        const row = table.insertRow();
        row.insertCell(0).innerText = date;
        row.insertCell(1).innerText = event;
        row.insertCell(2).innerText = location;
    }

    // Tampilkan form login saat halaman dimuat
    window.onload = function() {
        document.getElementById('login-form').style.display = 'block';
    };
</script>

</body>
</html>
