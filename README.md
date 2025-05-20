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

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">


    <title>GALLERY</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color:rgb(252, 252, 251);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 0 20px;
        }
        .gallery-container {
            width: 100%;
            max-width: 1200px;
            text-align: center;
        }
        h1 {
            margin-bottom: 30px;
            color: #222;
            font-size: 2rem;
        }
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        .gallery-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
        }
        .gallery-item .caption {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 10px;
            background: rgba(0, 0, 0, 0.6);
            color: #fff;
            font-size: 1rem;
            text-align: center;
            transform: translateY(100%);
            transition: transform 0.3s ease;
            opacity: 0;
        }
        .gallery-item:hover .caption {
            transform: translateY(0);
            opacity: 1;
        }
        .lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
            transition: opacity 0.3s ease;
        }
        .lightbox img {
            max-width: 90%;
            max-height: 80%;
            border-radius: 8px;
            transition: transform 0.3s ease;
        }
        .lightbox-close {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 2rem;
            color: #fff;
            cursor: pointer;
        }
        .lightbox.fade-in {
            display: flex;
            opacity: 1;
        }
        .lightbox.fade-out {
            opacity: 0;
            display: none;
        }
    </style>
</head>
<body>
    <div class="gallery-container">
        <h1>AJITHH'S PHOTO GALLERY</h1>
        <div class="gallery">
            <div class="gallery-item" data-image="1.jpeg">
                <img src="1.jpeg" alt="Photo 1">
                <div class="caption">Photo 1</div>
            </div>
            <div class="gallery-item" data-image="2.jpg">
                <img src="2.jpg" alt="Photo 2">
                <div class="caption">Photo 2</div>
            </div>
            <div class="gallery-item" data-image="3.jpeg">
                <img src="3.jpeg" alt="Photo 3">
                <div class="caption">Photo 3</div>
            </div>
            <div class="gallery-item" data-image="4.jpg">
                <img src="4.jpg" alt="Photo 4">
                <div class="caption">Photo 4</div>
            </div>
            
            </div>
        </div>
    </div>

    <div class="lightbox" id="lightbox">
        <span class="lightbox-close" id="lightbox-close">&times;</span>
        <img id="lightbox-image" src="1.jpg" alt="Large View">
    </div>
    <div class="lightbox" id="lightbox">
        <span class="lightbox-close" id="lightbox-close">&times;</span>
        <img id="lightbox-image" src="2.jpg" alt="Large View">
    </div>
    <div class="lightbox" id="lightbox">
        <span class="lightbox-close" id="lightbox-close">&times;</span>
        <img id="lightbox-image" src="3.jpg" alt="Large View">
    </div>
    <div class="lightbox" id="lightbox">
        <span class="lightbox-close" id="lightbox-close">&times;</span>
        <img id="lightbox-image" src="4.jpg" alt="Large View">
    </div>



    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const galleryItems = document.querySelectorAll('.gallery-item');
            const lightbox = document.getElementById('lightbox');
            const lightboxImage = document.getElementById('lightbox-image');
            const lightboxClose = document.getElementById('lightbox-close');

            galleryItems.forEach(item => {
                item.addEventListener('click', () => {
                    const imageSrc = item.getAttribute('data-image');
                    lightboxImage.src = imageSrc;
                    lightbox.classList.add('fade-in');
                });
            });

            
            lightboxClose.addEventListener('click', () => {
                lightbox.classList.add('fade-out');
                setTimeout(() => {
                    lightbox.classList.remove('fade-in', 'fade-out');
                    lightboxImage.src = '';
                }, 300);
            });

           
            lightbox.addEventListener('click', (e) => {
                if (e.target === lightbox) {
                    lightbox.classList.add('fade-out');
                    setTimeout(() => {
                        lightbox.classList.remove('fade-in', 'fade-out');
                        lightboxImage.src = '';
                    }, 300);
                }
            });
        });
    </script>
</body>
</html>
```


## OUTPUT
![alt text](<Screenshot (23).png>)
![alt text](<Screenshot (19).png>)
![alt text](<Screenshot (20).png>)
![alt text](<Screenshot (21).png>)
![alt text](<Screenshot (22).png>)
## RESULT
  The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
