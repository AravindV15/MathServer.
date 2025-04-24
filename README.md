# Ex.05 Design a Website for Server Side Processing
# Date:24/04/25
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
~~~
views:
from django.shortcuts import render

def triangle_area(request):
    area = None  # Initialize area to None for the first load
    if request.method == "POST":
        try:
            base = float(request.POST.get("base"))
            height = float(request.POST.get("height"))
            area = 0.5 * base * height  # Calculate the area
        except ValueError:
            area = "Invalid input. Please enter numeric values."
    
    return render(request, "triangle_area.html", {"area": area})
~~~
~~~
url:
from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('admin/', admin.site.urls),
     path('area/', views.triangle_area, name='triangle_area'),
]

~~~

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Triangle Area Calculator</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@400;700&display=swap');

        body {
            font-family: 'Libre Baskerville', serif; /* Royal font style */
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #8e44ad, #3498db, #f1c40f);
            background-size: 300% 300%;
            animation: gradientBG 6s ease infinite;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #fff;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-size: 2rem;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }

        label {
            font-size: 1.1rem;
            font-weight: bold;
            margin-bottom: 10px;
            display: block;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.4);
        }

        input {
            background: rgba(255, 255, 255, 0.9);
            border: none;
            border-radius: 10px;
            width: calc(100% - 30px);
            padding: 12px 15px;
            margin: 10px 0;
            font-size: 1rem;
            color: #555;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        }

        button {
            background-color: #e74c3c;
            color: white;
            border: none;
            padding: 12px 25px;
            margin-top: 20px;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            transition: transform 0.2s, background-color 0.3s;
        }

        button:hover {
            background-color: #c0392b;
            transform: scale(1.05);
        }

        .box {
            margin: 15px 0;
            padding: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
        }

        h2 {
            color: #f1c40f;
            margin-top: 20px;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.6);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Triangle Area Calculator</h1>
        <form method="post">
            {% csrf_token %}
            <div class="box">
                <label for="base">Base:</label>
                <input type="number" id="base" name="base" step="any" required>
            </div>
            <div class="box">
                <label for="height">Height:</label>
                <input type="number" id="height" name="height" step="any" required>
            </div>
            <div class="box">
                <button type="submit">Calculate Area</button>
            </div>
        </form>
        {% if area is not None %}
            <h2>Area of the Triangle: {{ area }}</h2>
        {% endif %}
    </div>
</body>
</html>
~~~
# SERVER SIDE PROCESSING:
![image](https://github.com/user-attachments/assets/b542b102-8117-4bee-87a5-fdc3e57b134b)



# HOMEPAGE:
![image](https://github.com/user-attachments/assets/23b9e4ab-e299-4854-a2b7-c8fe29a76e8b)



# RESULT:
The program for performing server side processing is completed successfully.
