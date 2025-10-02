<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>Student Information Form</title>
</head>
<body>
    <form>
        <label for="id">Enter ID</label>
        <input type="text" id="id" name="id" />

        <label for="lastname">Enter Last Name</label>
        <input type="text" id="lastname" name="lastname" />

        <label for="firstname">Enter First Name</label>
        <input type="text" id="firstname" name="firstname" />

        <label for="middlename">Enter Middle Name</label>
        <input type="text" id="middlename" name="middlename" />

        <label for="course">Enter Course</label>
        <input type="text" id="course" name="course" />

        <label for="section">Enter Section</label>
        <input type="text" id="section" name="section" />

        <input type="submit" value="Submit" />
    </form>

    <table>
        <thead>
            <tr>
                <th>ID Number</th>
                <th>Last Name</th>
                <th>First Name</th>
                <th>Middle Name</th>
                <th>Course</th>
                <th>Section</th>
            </tr>
        </thead>
          
    </table>
</body>
</html>
      <label>Enter Section</label>
      <input type="text" name="section" required>

      <button type="submit">Submit</button>
    </form>
  </div>
</body>
</html>



body {
    background-color: #f4d9dd;
    font-family: Arial, sans-serif;
}

form {
    background-color: #abe0e3;
    padding: 20px;
    width: 350px;
    margin: 20px auto;
    border: 1px solid #5e8286;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    align-items: center;
}

form label {
    font-weight: bold;
    justify-self: end;
}

form input[type="text"] {
    width: 180px;
    padding: 5px;
}

form input[type="submit"] {
    grid-column: 2 / 3;
    justify-self: start;
    padding: 5px 10px;
    font-weight: bold;
    cursor: pointer;
}

table {
    margin: 20px auto;
    border-collapse: collapse;
    width: 80%;
    background-color: #fff;
}

table, th, td {
    border: 1px solid #ccc;
    text-align: center;
    padding: 8px;
}

th {
    background-color: #f2f2f2;
}
