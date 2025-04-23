# Nexus-Portal 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href= "https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f5f5f5;
            margin: 0 auto;
            padding: 2rem;
        }
        .container {
            max-width: 100px;
            margin: 0 auto;
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            margin-bottom: 2rem;
        }
        .nav {
            display: flex;
            justify-content: space-around;
            margin-bottom: 2rem;
            flex-wrap;
        }
        .nav-button {
            background-color: #007bff;
            color: white;
            padding: 0.75rem, 1.5rem;
            margin: 0.5rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }
        section {
            display: none;
        }
        section.active {
            display: block;
        }
        iframe {
            width: 100%;
            height: 600px;
            border: none;
        }
        table {
            width: 100%;
            margin-top: 1rem;
            border-collapse: collapse;
        }
        th, td {
            padding: 0.75rem;
            border: 1px solid #ddd;
            text-align: left;
        }
        th {
            background-color: #f0f0f0;
        }
    </style>
   </head>
<body>
    <div class="container">
        <h1> Nexus Payroll Admin Portal</h1>
        <div class="nav">
        <button onclick="showSection('overview')">Overview</button>
        <button onclick="showSection('pseudocode')">Pseudocode</button>
        <button onclick="showSection('flowchart')">Flowchart</button>
        <button onclick="showSection('payroll')">Payroll</button>
    </div>
    <section id="overview" class="active">
        <h2>Project Overview</h2>
        <p>This portal presents the final payroll system project, including the live payroll calculator, pseudocode, flowchart diagram, and payroll entries.</p>
        <ul>
            <li><strong>Team Members:</strong> Madeline Plank, Raidan George, and David Kidwell</li>
            <li><strong>Tools Used:</strong> HTML, JavaScript, Excel, Flowcharts, Pseudocode, Canvas.</li>
            <li><strong>Key Features:</strong> Gross pay + Tax calculator, overtime data handling</li>
        </ul>
    </section>
    <section id="pseudocdoe">
        <h2>Pseudocode</h2>
        <iframe src="pseudocode.pdf"></iframe>
    </section>
    <section id="flowchart">
        <h2><Flowchart</h2>
        <iframe src="flowchart.png"></iframe>
    </section>
    <section id="payroll">
        <h2><Payrol</h2>
        <div id="payrollTableWrapper">
            <table id="payrollTable">
                <thead>
                    <tr>
                        <th>Employee</th>
                        <th>ID</th>
                        <th>Gross Pay</th>
                        <th>State Tac</th>
                        <th>Federal Tac</th>
                        <th>Net Pay</th>
                    </tr>
                </thead>
                <tbody id="payrollBody">
                </tbody>
            </table>
        </div>
    </section>
</div>
<script>
    function showSection(sectionID) {
        document.querySelectorAll('section').forEach(sec => {
            sec.classList.remove('active');
        }):
    }
    const employees = [
        { name: "Caleb Morris", id: "1000", gross: 1320, state: 73.92, federal: 104.28 },
        {name: "Jasmine Wright", id: "1001", gross: 1417.50, state: 69.38, federal: 111.98 },
        { name: "Devon Robinson", id: "1002", gross: 1320, state: 73.92, federal: 104.28 },
        { name: "Allison Turner", id: "1003", gross: 0, state: 0, federal: 0 },
        { name: "Raul Garcia", id: "1004", gross: 1050, state: 58.8, federal: 82.95},
        { name: "Sean Barker", id: "1005", gross: 1462, state: 81.872, federal: 115.498 },
        { name: "Isabella Flores", id: "1006", gross: 2310, state: 129.36, federal: 182.49 },
        { name: "Aaliyah Ellis", id: "1007", gross: 1662.50, state: 93.1, federal: 131.3375 },
        { name: "Jordan Davis", id: "1008", gross: 0, state: 0, federal: 0 },
        { name: "Victoria Parker", id: "1009", gross: 1320, state: 73.92, federal: 104.28},
    ];
    const body = document.getElementByID('payrollBody');
    employees.forEach(emp => {
        const net = emp.gross - emp.state - emp.federal;
        const row = document.createElement('tr');
        row.innerHTML = 
            <td>${emp.name}</td>
            <td>${emp.id}</td>
            <td>$${emp.gross.toFixed(2)}</td>
            <td>$${emp.state.toFixed(2)}</td>
            <td>$${emp.federal.toFixed(2)}</td>
            <td>$${net.toFixed(2)}</td>
            ;
            body.appendChild(row);
    });
</script>
</body>
</html>
