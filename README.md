<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        .machine-container {
            display: flex;
            flex-wrap: wrap;
            width: 800px;
            height: 800px;
        }

        .machine {
            position: relative;
            width: 150px;
            height: 150px;
            margin: 5px;
            border: 1px solid #ccc;
            box-sizing: border-box;
        }

        .machine-number {
            position: absolute;
            top: 0;
            left: 0;
            width: 10px;
            height: 10px;
            background-color: #333;
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .machine-center {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .mac-data-div {
            max-height: 100px; /* Set a maximum height for the scroll */
            overflow-y: auto; /* Enable vertical scroll */
        }

        table {
            border-collapse: collapse;
            width: 100%;
        }

        table, th, td {
            border: 1px solid #ddd;
        }

        th, td {
            padding: 8px;
            text-align: left;
        }

        th {
            display: none; /* Hide table headers */
        }
    </style>
    <script>
        document.addEventListener("DOMContentLoaded", function () {
            // Create machine divs
            const machineContainer = document.getElementById("machine-container");

            for (let i = 1; i <= 30; i++) {
                const machineDiv = document.createElement("div");
                machineDiv.className = "machine";
                machineDiv.id = "mac" + i;

                const numberDiv = document.createElement("div");
                numberDiv.className = "machine-number";
                numberDiv.textContent = i;

                const centerDiv = document.createElement("div");
                centerDiv.className = "machine-center";

                const macDataDiv = document.createElement("div");
                macDataDiv.className = "mac-data-div";

                // Sample data for demonstration purposes
                const jsonData = [
                    { name: "Data1", value: "100" },
                    { name: "Data2", value: "200" },
                    { name: "Data3", value: "300" }
                ];

                const table = document.createElement("table");
                jsonData.forEach(item => {
                    const row = table.insertRow();
                    const cell1 = row.insertCell(0);
                    const cell2 = row.insertCell(1);
                    cell1.textContent = item.name;
                    cell2.textContent = item.value;
                });

                macDataDiv.appendChild(table);
                centerDiv.appendChild(macDataDiv);
                machineDiv.appendChild(numberDiv);
                machineDiv.appendChild(centerDiv);
                machineContainer.appendChild(machineDiv);
            }
        });
    </script>
</head>
<body>
    <div id="machine-container" class="machine-container"></div>
</body>
</html>
