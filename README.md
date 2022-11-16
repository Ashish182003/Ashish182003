- 👋 Hi, I’m @Ashish182003

<!DOCTYPE html PUBLIC "-//ashish//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
    <style type="text/css">
        body
        {
            font-family: Arial;
            font-size: 10pt;
        }
        table
        {
            border: 1px solid #ccc;
            border-collapse: collapse;
        }
        table th
        {
            background-color: #F7F7F7;
            color: #333;
            font-weight: bold;
        }
        table th, table td
        {
            padding: 5px;
            border-color: #ccc;
        }
    </style>
</head>
<body>
    <input type="button" value="Generate Table" onclick="GenerateTable()" />
    <hr />
    <div id="dvTable">
    </div>
    <script type="text/javascript">
        function GenerateTable() {
            //Build an array containing Customer records.
            var customers = new Array();
            customers.push(["Customer Id", "Name", "Country"]);
            customers.push([1, "John Hammond", "United States"]);
            customers.push([2, "Mudassar Khan", "India"]);
            customers.push([3, "Suzanne Mathews", "France"]);
            customers.push([4, "Robert Schidner", "Russia"]);

            //Create a HTML Table element.
            var table = document.createElement("TABLE");
            table.border = "1";

            //Get the count of columns.
            var columnCount = customers[0].length;

            //Add the header row.
            var row = table.insertRow(-1);
            for (var i = 0; i < columnCount; i++) {
                var headerCell = document.createElement("TH");
                headerCell.innerHTML = customers[0][i];
                row.appendChild(headerCell);
            }

            //Add the data rows.
            for (var i = 1; i < customers.length; i++) {
                row = table.insertRow(-1);
                for (var j = 0; j < columnCount; j++) {
                    var cell = row.insertCell(-1);
                    cell.innerHTML = customers[i][j];
                }
            }

            var dvTable = document.getElementById("dvTable");
            dvTable.innerHTML = "";
            dvTable.appendChild(table);
        }
    </script>
</body>
</html>
