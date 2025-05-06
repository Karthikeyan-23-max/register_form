# register_form
program
```
<!DOCTYPE html>
<html>
<head>
  <title>Registration Form</title>
  <style>
    body {
      background-color: #f2f2f2;
      font-family: Arial, sans-serif;
    }
    .form-container {
      background-color: #ccf6f9;
      width: 400px;
      margin: 50px auto;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px #aaa;
    }
    h2 {
      text-align: center;
      color: blue;
    }
    label {
      display: block;
      margin-top: 10px;
      font-weight: bold;
    }
    input[type="text"], input[type="date"], select, textarea {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
    }
    .gender, .qualification {
      margin-top: 5px;
    }
    input[type="submit"], input[type="reset"] {
      margin-top: 15px;
      padding: 10px 20px;
    }
  </style>
</head>
<body>
  <div class="form-container">
    <h2>Registration Form</h2>
    <form>
      <label>First Name*:</label>
      <input type="text" required>

      <label>Last Name*:</label>
      <input type="text" required>

      <label>Gender*:</label>
      <div class="gender">
        <input type="radio" name="gender" required> Male
        <input type="radio" name="gender"> Female
        <input type="radio" name="gender"> Transgender
      </div>

      <label>Date of Birth*:</label>
      <input type="date" id="dob" required onchange="calculateAge()">

      <label>Age:</label>
      <input type="text" id="age" readonly>

      <label>Nationality*:</label>
      <select required>
        <option value="">--Choose an option--</option>
        <option value="Indian">Indian</option>
        <option value="Other">Other</option>
      </select>

      <label>Educational Qualification*:</label>
      <div class="qualification">
        <input type="checkbox"> +2
        <input type="checkbox"> Diploma
        <input type="checkbox"> UG
        <input type="checkbox"> PG
      </div>

      <label>Upload Your Resume*:</label>
      <input type="file" required>

      <label>Declaration*:</label>
      <textarea rows="3" required></textarea>

      <input type="submit" value="Submit">
      <input type="reset" value="Reset">
    </form>
  </div>

  <script>
    function calculateAge() {
      const dob = new Date(document.getElementById('dob').value);
      const today = new Date();
      let age = today.getFullYear() - dob.getFullYear();
      const m = today.getMonth() - dob.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < dob.getDate())) {
        age--;
      }
      document.getElementById('age').value = age;
    }
  </script>
</body>
</html>
```
output
![Screenshot 2025-05-06 125719](https://github.com/user-attachments/assets/eab6e01c-5f34-4353-9582-1a0e32e44557)
