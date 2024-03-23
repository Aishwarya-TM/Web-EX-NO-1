# EX01 Developing a Simple Webserver
## Date: 23.03.2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Web Site</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
  <link rel="stylesheet" href="assests/css/style.css">
</head>


<body>
  <div class="row">
    <div class="col-5">
      <a href=""><i class="bi bi-twitter"></i> </a>
      <a href=""><i class="bi bi-youtube"></i></a>
      <a href=""><i class="bi bi-facebook"></i></a>
      <a href=""><i class="bi bi-linkedin"></i></a>
      <a href=""><i class="bi bi-pinterest"></i></a>
      <a href=""><i class="bi bi-whatsapp"></i></a>
      <a href=""><i class="bi bi-instagram"></i></a>

    </div>
    <div class="col-5" style="padding-left: 150px;">
      <a href="">Alumini</a><i class="bi bi-three-dots-vertical"></i>
      <a href="">Events</a><i class="bi bi-three-dots-vertical"></i>
      <a href="">Career</a><i class="bi bi-three-dots-vertical"></i>
      <a href="">Login</a><i class="bi bi-three-dots-vertical"></i>
      <a href="">SEC Portal</a>

    </div>
    <div class="col-2" style="padding-right: 15px;">
      <div class="search">
        <i class="bi bi-search"></i>
        <input type="search" name="" placeholder="search" style="background-color: #f3f3f3;border: 0px;outline: none;">
      </div>
    </div>
  </div>
  <div class="main">
    <div class="col-4">
      <img src="assests/css/logo.png" alt="" width="500px" height="65px" style="padding-left: 30px;">
    </div>
    <div class="col-6">
      <div class="menu">
        <a href="">Home</a>
        <a href="">About</a>
        <a href="">Departments</a>
        <a href="">Life at SEC</a>
        <a href="">Admission</a>
        <a href="">Placements</a>
        <a href="">Research</a>
      </div>
    </div>
    <div class="col-2">
      <p id="text">For Admission</p>
    </div>
  </div>
  <div class="row3">
    <div class="col-3">
      <img id='imag' src="assests/css/Screenshot 2024-03-13 200329.png" alt="">
    </div>
    <div class="col-9" id="carousel">
      <div id="carouselExampleIndicators" class="carousel slide">
        <div class="carousel-indicators">
          <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active"
            aria-current="true" aria-label="Slide 1"></button>
          <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1"
            aria-label="Slide 2"></button>
          <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2"
            aria-label="Slide 3"></button>
          <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="3"
            aria-label="Slide 4"></button>
          <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="4"
            aria-label="Slide 5"></button>
          <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="5"
            aria-label="Slide 6"></button>
        </div>
        <div class="carousel-inner">
          <div class="carousel-item active">
            <img src="assests/css/1.jpeg.jpg" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="assests/css/2.jpg" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="assests/css/3.PNG" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="assests/css/Screenshot 2024-03-23 134027.png" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="assests/css/Screenshot 2024-03-23 134040.png" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="assests/css/Screenshot 2024-03-23 134100.png" class="d-block w-100" alt="..." />
          </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators"
          data-bs-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators"
          data-bs-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
  <div class="images">
   <div id="img1">
    <img src="assests/css/Screenshot 2024-03-23 134549.png" alt="">
   </div>
   <div id="img2">
    <img src="assests/css/Screenshot 2024-03-23 134557.png" alt="">
   </div>
   <div id="img3">
    <img src="assests/css/Screenshot 2024-03-23 134604.png" alt="">
   </div>
   <div id="img4">
    <img src="assests/css/Screenshot 2024-03-23 134611.png" alt="">
   </div>
   <div id="img5">
    <img src="assests/css/Screenshot 2024-03-23 134619.png" alt="">
   </div>
   
  </div>
  <div class="row5">
    <div class="col-3" id="div1">
      <img src="assests/css/Screenshot 2024-03-23 141103.png" >
    </div>
    <div class="col-6" id="div2">
      <img src="assests/css/Screenshot 2024-03-23 141539.png" alt="" width="700px">
      <p>
        SEC is a leading Engineering College located in Chennai, India., which offers a global approach to education and research, with a focus on global perspectives and expertise. SEC offers a wide range of undergraduate, postgraduate and doctoral programs in Engineering. Some of its Academic Highlights are,

Only Engineering College in India to have 30 students per class.
91% results in University exam.
173 University Ranks.
Compulsory internship every year. 
      </p>
    </div>
    <div class="col-3" id="div3">
      <h4>
        Latest Events
      </h4>
      <br>
      <p class="date">
        19 Mar 2024;
        </p>
        <p class="event">
        A warm welcome to HR Team of 'Foxconn Industrial Internet'.
      </p>
      <hr>
      <p class="date">
        21 Mar 2024;
      </p>
      <p class="event">
       MBA Final Year learners bagged a coveted placement at 'HDB Financial Services'
      </p>
      <hr>
    <p class="date">16 Mar 2024;
      </p>
      <p class="event">
      SEC kick started cultural fest - CELANZA’24 with a Big Bang</p>
    </div>
  </div>
  <div class="row6">
    <div class="col-4">
      <img src="assests/css/logo.png" alt="" width="400px" height="65px">
    </div>
    <div class="col-2" id="icon1">
      <a href="#">
        <i class="bi bi-envelope"></i>  Contact Us Today
      </a>
    </div>
    <div class="col-3" id="icon2">
      <a href="#">
        <i class="bi bi-telephone"></i> +91 4466726677
      </a>
    </div>

    <div class="col-3" id="icon3">
      <a href="#">
        <i class="bi bi-telephone"></i> +91 4466726690
      </a>
    </div>

  </div>



    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
      crossorigin="anonymous"></script>

</body>

</html>
"""
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
![alt text](<Screenshot 2024-03-23 201519.png>)
![Screenshot 2024-03-23 201610](https://github.com/Aishwarya-TM/Web-EX-NO-1/assets/127846109/e27c4bc8-417a-487e-ae99-e52b213a567f)
![alt text](<Screenshot 2024-03-23 201638.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
