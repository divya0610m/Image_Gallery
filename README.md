# Ex.08 Design of Interactive Image Gallery

## AIM
  To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS

## Step 1:

Clone the github repository and create Django admin interface

## Step 2:

Change settings.py file to allow request from all hosts.

## Step 3:

Use CSS for positioning and styling.

## Step 4:

Write JavaScript program for implementing interactivit

## Step 5:

Validate the HTML and CSS code

## Step 6:

Publish the website in the given URL.

## PROGRAM
```
img.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Image Gallery</title>
  <style>
    body {
      font-family: sans-serif;
      background-color:violet;
      padding: 2rem;
      margin: 0;
      text-align: center;
      color:white;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 15px;
      max-width: 600px;
      margin: auto;
      
    }

    .gallery img {
      width: 100%;
      height: auto;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    .gallery img:hover {
      transform: scale(1.05);
    }

    .lightbox {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: rgba(0, 0, 0, 0.9);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 999;
      flex-direction: column;
    }

    .lightbox img {
      max-width: 90%;
      max-height: 90vh;
      border-radius: 10px;
    }

    .controls {
      position: absolute;
      top: 50%;
      width: 100%;
      display: flex;
      justify-content: space-between;
      padding: 0 30px;
      color: white;
      font-size: 3rem;
      user-select: none;
      transform: translateY(-50%);
    }

    .controls span {
      cursor: pointer;
      padding: 0 10px;
      background: rgba(0,0,0,0.4);
      border-radius: 5px;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 30px;
      color: white;
      font-size: 2rem;
      cursor: pointer;
      background: rgba(0,0,0,0.4);
      padding: 5px 10px;
      border-radius: 5px;
    }
  </style>
</head>
<body>

  <h1>Interactive Image Gallery</h1>

  <div class="gallery">
    <img src="pic 2.jpg" alt="Cat 1" />
    <img src="pic 3.jpg" alt="Cat 2" />
    <img src="pic 1.jpg" alt="Cat 3" />
    <img src="pic 4.jpg" alt="Cat 4" />
    <img src="pic 6.jpg" alt="Cat 5" />
    <img src="pic 7.jpg" alt="Cat 5" />

  </div>

  <div class="lightbox" id="lightbox">
    <span class="close" id="closeBtn">&times;</span>
    <div class="controls">
      <span id="prev">&#10094;</span>
      <span id="next">&#10095;</span>
    </div>
    <img id="lightbox-img" src="" alt="Enlarged" />
  </div>

  <script>
    const images = document.querySelectorAll('.gallery img');
    const lightbox = document.getElementById('lightbox');
    const lightboxImg = document.getElementById('lightbox-img');
    const closeBtn = document.getElementById('closeBtn');
    const nextBtn = document.getElementById('next');
    const prevBtn = document.getElementById('prev');

    let currentIndex = 0;

    function showImage(index) {
      currentIndex = index;
      lightboxImg.src = images[currentIndex].src;
      lightbox.style.display = 'flex';
    }

    images.forEach((img, index) => {
      img.addEventListener('click', () => {
        showImage(index);
      });
    });

    closeBtn.addEventListener('click', () => {
      lightbox.style.display = 'none';
    });

    nextBtn.addEventListener('click', () => {
      currentIndex = (currentIndex + 1) % images.length;
      showImage(currentIndex);
    });

    prevBtn.addEventListener('click', () => {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      showImage(currentIndex);
    });

    // Optional: Close on outside click
    lightbox.addEventListener('click', (e) => {
      if (e.target === lightbox || e.target === lightboxImg) {
        lightbox.style.display = 'none';
      }
    });
  </script>

</body>
</html>

```

## OUTPUT

![alt text](<Screenshot 2025-05-20 132251.png>)
![alt text](<Screenshot 2025-05-20 132306.png>)
![alt text](<Screenshot 2025-05-20 132324.png>)
![alt text](<Screenshot 2025-05-20 132338.png>)

## RESULT
  The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
