# Ex.05 Design a Website for Server Side Processing
# Date:19.10.24
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
HTML:
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lamp Filament Power Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      text-align: center;
      background-color: #f4f4f4;
    }
    .container {
      max-width: 500px;
      margin: 50px auto;
      padding: 20px;
      background: white;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
    }
    h1 {
      color: #333;
    }
    input {
      margin: 10px 0;
      padding: 10px;
      width: 80%;
      font-size: 1rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px 20px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1rem;
      cursor: pointer;
    }
    button:hover {
      background-color: #0056b3;
    }
    .output {
      margin-top: 20px;
      font-size: 1.2rem;
      color: #333;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Lamp Filament Power Calculator</h1>
    <p>Enter the intensity (I) and resistance (R) below:</p>
    <input type="number" id="intensity" placeholder="Intensity (I) in amps" />
    <input type="number" id="resistance" placeholder="Resistance (R) in ohms" />
    <button onclick="calculatePower()">Calculate Power</button>
    <div class="output" id="output"></div>
  </div>

  <script>
    function calculatePower() {
      // Get input values
      const intensity = parseFloat(document.getElementById('intensity').value);
      const resistance = parseFloat(document.getElementById('resistance').value);

      // Validate inputs
      if (isNaN(intensity) || isNaN(resistance) || intensity <= 0 || resistance <= 0) {
        document.getElementById('output').innerText = "Please enter valid positive numbers for intensity and resistance.";
        return;
      }

      // Calculate power
      const power = Math.pow(intensity, 2) * resistance;

      // Display result
      document.getElementById('output').innerText = `Power (P) = ${power.toFixed(2)} watts`;
    }
  </script>
</body>
</html>

views.py
from django.shortcuts import render

def serverside(request):
    return render(request,'serverside.html')

urls.py
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('app.urls')),  # Include the app's URLs
]

# SERVER SIDE PROCESSING:
![Screenshot 2024-12-13 101705](https://github.com/user-attachments/assets/6ae260ff-5a9c-46d4-94d2-398e77beb882)


# HOMEPAGE:
![Screenshot 2024-12-13 101823](https://github.com/user-attachments/assets/4192fc00-c4ae-4e26-9037-4263ce751a9c)


# RESULT:
The program for performing server side processing is completed successfully.
