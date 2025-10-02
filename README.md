<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Student Form — Demo</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <main class="page">
    <section class="form-area">
      <form id="studentForm" class="card" autocomplete="off">
        <h2>Student Info</h2>

        <label for="idNumber">Enter ID</label>
        <input id="idNumber" name="idNumber" type="text" placeholder="ID Number">

        <label for="lastName">Enter Last Name</label>
        <input id="lastName" name="lastName" type="text" placeholder="Last Name">

        <label for="firstName">Enter First Name</label>
        <input id="firstName" name="firstName" type="text" placeholder="First Name">

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
