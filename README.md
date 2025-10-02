<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Student Form</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="form-container">
    <form id="studentForm">
      <table>
        <tr>
          <td><label for="idNumber">Enter ID</label></td>
          <td><input type="text" id="idNumber" name="idNumber"></td>
        </tr>
        <tr>
          <td><label for="lastName">Enter Last Name</label></td>
          <td><input type="text" id="lastName" name="lastName"></td>
        </tr>
        <tr>
          <td><label for="firstName">Enter First Name</label></td>
          <td><input type="text" id="firstName" name="firstName"></td>
        </tr>
        <tr>
          <td><label for="middleName">Enter Middle Name</label></td>
          <td><input type="text" id="middleName" name="middleName"></td>
        </tr>
        <tr>
          <td><label for="course">Enter Course</label></td>
          <td><input type="text" id="course" name="course"></td>
        </tr>
        <tr>
          <td><label for="section">Enter Section</label></td>
          <td><input type="text" id="section" name="section"></td>
        </tr>
        <tr>
          <td colspan="2" style="text-align:right;">
            <button type="submit">Submit</button>
          </td>
        </tr>
      </table>
    </form>
  </div>

  <div class="table-container">
    <table id="studentsTable" border="1">
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
      <tbody>
        <!-- Sample row -->
        <tr>
          <td>12345</td>
          <td>De Guzman</td>
          <td>Richard</td>
          <td>De Leon</td>
          <td>BSIT</td>
          <td>IT203</td>
        </tr>
      </tbody>
    </table>
  </div>

  <script>
    // Add data to table
    document.getElementById('studentForm').addEventListener('submit', function(e){
      e.preventDefault();

      const id = document.getElementById('idNumber').value;
      const last = document.getElementById('lastName').value;
      const first = document.getElementById('firstName').value;
      const middle = document.getElementById('middleName').value;
      const course = document.getElementById('course').value;
      const section = document.getElementById('section').value;

      const table = document.getElementById('studentsTable').getElementsByTagName('tbody')[0];
      const newRow = table.insertRow();

      [id,last,first,middle,course,section].forEach(text=>{
        let cell = newRow.insertCell();
        cell.textContent = text;
      });

      this.reset();
    });
  </script>
</body>
</html>
        <label for="middleName">Enter Middle Name</label>
        <input id="middleName" name="middleName" type="text" placeholder="Middle Name">

        <label for="course">Enter Course</label>
        <input id="course" name="course" type="text" placeholder="Course">

        <label for="section">Enter Section</label>
        <input id="section" name="section" type="text" placeholder="Section">

        <div class="actions">
          <button type="submit" id="submitBtn">Submit</button>
        </div>
      </form>
    </section>

    <section class="table-area">
      <table id="studentsTable" class="styled-table">
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
        <tbody>
          <!-- Sample rows (you can remove or keep) -->
          <tr>
            <td>12345</td>
            <td>De Guzman</td>
            <td>Richard</td>
            <td>De Leon</td>
            <td>BSIT</td>
            <td>IT203</td>
          </tr>
          <tr>
            <td>56789</td>
            <td>Garcia</td>
            <td>Marcos</td>
            <td>Santos</td>
            <td>BSCS</td>
            <td>CS101</td>
          </tr>
        </tbody>
      </table>
    </section>
  </main>

  <script>
    // Add form data to table
    document.getElementById('studentForm').addEventListener('submit', function (e) {
      e.preventDefault();

      const id = document.getElementById('idNumber').value.trim();
      const last = document.getElementById('lastName').value.trim();
      const first = document.getElementById('firstName').value.trim();
      const middle = document.getElementById('middleName').value.trim();
      const course = document.getElementById('course').value.trim();
      const section = document.getElementById('section').value.trim();

      // Simple validation: at least ID and Last & First name required
      if (!id || !last || !first) {
        alert('Please enter ID, Last Name and First Name.');
        return;
      }

      const tbody = document.querySelector('#studentsTable tbody');
      const tr = document.createElement('tr');

      [id, last, first, middle, course, section].forEach(text => {
        const td = document.createElement('td');
        td.textContent = text;
        tr.appendChild(td);
      });

      tbody.appendChild(tr);

      // Clear form
      this.reset();
      document.getElementById('idNumber').focus();
    });
  </script>
</body>
</html>
