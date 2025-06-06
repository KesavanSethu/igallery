# Ex.08 Design of Interactive Image Gallery
## Date:25/04/2025

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>SUPERMAN</title>

  <!-- Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Bangers&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: rgb(0, 26, 255);
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      height: 100vh;
      overflow: hidden;
    }

    .title {
      font-family: 'Bangers', cursive;
      font-size: 40px;
      color: rgb(187, 255, 0);
      margin-top: 10px;
    }

    .gallery-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: repeat(2, 1fr);
      gap: 15px;
      padding: 15px;
      width: 95%;
      max-width: 1000px;
      flex-grow: 1;
      overflow: hidden;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 10px;
      transition: transform 0.3s;
    }

    .gallery-item:hover img {
      transform: scale(1.05);
      cursor: pointer;
    }

    .gallery-item {
      overflow: hidden;
      border-radius: 10px;
    }

    .slider {
      display: none;
      position: fixed;
      z-index: 2;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.85);
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    .slider img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 10px;
    }

    .arrow {
      cursor: pointer;
      position: absolute;
      top: 50%;
      font-size: 40px;
      color: cyan;
      user-select: none;
      padding: 10px;
    }

    .arrow.left {
      left: 20px;
    }

    .arrow.right {
      right: 20px;
    }

    .close-btn {
      position: absolute;
      top: 10px;
      right: 20px;
      background-color: transparent;
      color: cyan;
      border: none;
      font-size: 30px;
      cursor: pointer;
    }

    .footer {
      font-family: 'Roboto', sans-serif;
      font-size: 13px;
      color: red;
      margin: 10px;
    }

    @media (max-width: 768px) {
      .gallery-container {
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(3, 1fr);
      }
    }

    @media (max-width: 500px) {
      .gallery-container {
        grid-template-columns: 1fr;
        grid-template-rows: repeat(6, 1fr);
      }
    }
  </style>
</head>
<body>
  <div class="title">SUPERMAN</div>

  <div class="gallery-container">
    <div class="gallery-item"><img src="C:\Users\admin\igallery\vijay\clacapp\static\9acfd412f2241ea9dd1bf327e665f332.jpg" alt="Image 1" /></div>
    <div class="gallery-item"><img src="C:\Users\admin\igallery\vijay\clacapp\static\201-1.jpg" alt="Image 2" /></div>
    <div class="gallery-item"><img src="C:\Users\admin\igallery\vijay\clacapp\static\441aa43bdab03687b7528e0552ccc56a.jpg" alt="Image 3" /></div>
    <div class="gallery-item"><img src="C:\Users\admin\igallery\vijay\clacapp\static\b34e3c75-2524-4e2c-be3a-64761a1addc0.jpg" alt="Image 4" /></div>
    <div class="gallery-item"><img src="C:\Users\admin\igallery\vijay\clacapp\static\superman_1_var.jpg" alt="Image 5" /></div>
    <div class="gallery-item"><img src="C:\Users\admin\igallery\vijay\clacapp\static\when-someone-says-iconic-superman-cover-which-one-springs-v0-qn96cwkkehxc1.jpg" alt="Image 6" /></div>
  </div>

  <div class="slider" id="slider">
    <button class="close-btn" id="close-btn">&#10006;</button>
    <span class="arrow left" id="prev">&#10094;</span>
    <img src="" alt="Slider Image" id="slider-img" />
    <span class="arrow right" id="next">&#10095;</span>
  </div>

  <div class="footer">Developed by Kesavan S</div>

  <script>
    const images = document.querySelectorAll('.gallery-item img');
    const slider = document.getElementById('slider');
    const sliderImg = document.getElementById('slider-img');
    const prevBtn = document.getElementById('prev');
    const nextBtn = document.getElementById('next');
    const closeBtn = document.getElementById('close-btn');
    let currentIndex = 0;

    images.forEach((image, index) => {
      image.addEventListener('click', () => {
        slider.style.display = 'flex';
        sliderImg.src = image.src;
        currentIndex = index;
        document.body.style.overflow = 'hidden';
      });
    });

    prevBtn.addEventListener('click', (e) => {
      e.stopPropagation();
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      sliderImg.src = images[currentIndex].src;
    });

    nextBtn.addEventListener('click', (e) => {
      e.stopPropagation();
      currentIndex = (currentIndex + 1) % images.length;
      sliderImg.src = images[currentIndex].src;
    });

    closeBtn.addEventListener('click', () => {
      slider.style.display = 'none';
      document.body.style.overflow = 'auto';
    });

    slider.addEventListener('click', () => {
      slider.style.display = 'none';
      document.body.style.overflow = 'auto';
    });
  </script>
</body>
</html>


```

## OUTPUT:

![Alt text](<Screenshot (58).png>)
![Alt text](<Screenshot (59).png>)
![Alt text](<Screenshot (60).png>)
![Alt text](<Screenshot (61).png>)
![Alt text](<Screenshot (62).png>)
![Alt text](<Screenshot (63).png>)
![Alt text](<Screenshot (64).png>)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
