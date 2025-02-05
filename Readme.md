# Image Slider

## Overview
This project is a simple image slider (carousel) built using HTML and CSS. It allows users to navigate through multiple images using radio buttons and styled dots.

## Project Structure
/slider-project ├── index.html # Main HTML file ├── style.css # CSS for styling ├── 1.jpg # Image 1 ├── 2.jpg # Image 2 ├── 3.jpg # Image 3 ├── 4.jpg # Image 4

php-template
Copy
Edit

## 1. index.html (HTML Structure)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Slider</title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <div class="slider">
        <div class="images">
            <input type="radio" name="slide" id="img1" checked>
            <input type="radio" name="slide" id="img2">
            <input type="radio" name="slide" id="img3">
            <input type="radio" name="slide" id="img4">

            <img src="./1.jpg" class="m1" alt="img1">
            <img src="./2.jpg" class="m2" alt="img2">
            <img src="./3.jpg" class="m3" alt="img3">
            <img src="./4.jpg" class="m4" alt="img4">
        </div>
        <div class="dots">
            <label for="img1"></label>
            <label for="img2"></label>
            <label for="img3"></label>
            <label for="img4"></label>
        </div>
    </div>
</body>
</html>
```
Explanation
<input type="radio">: These radio buttons allow users to switch between images. The name="slide" ensures only one radio button is selected at a time. The id="img1" links each button to an image. The checked attribute on img1 sets it as the default image.
<img>: Images are added with classes (.m1, .m2, .m3, .m4) for styling.
Navigation Dots (<label> for radio buttons): Labels act as selectors for images. Clicking a dot changes the selected image.
2. style.css (CSS Styling)
css
Copy
```
/* Global Styles */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgb(25,12,41);
}

/* Slider Container */
.slider {
    position: relative;
    width: 60%;
    overflow: hidden;
}

/* Image Wrapper */
.images {
    display: flex;
    width: 100%;
}

.images img {
    height: 400px;
    width: 100%;
    transition: all 0.15s ease;
}

.images input {
    display: none; /* Hide radio buttons */
}

/* Navigation Dots */
.dots {
    display: flex;
    justify-content: center;
    margin: 5px;
}

.dots label {
    height: 20px;
    width: 20px;
    border-radius: 50%;
    border: solid #fff 3px;
    cursor: pointer;
    transition: all 0.15s ease;
    margin: 5px;
}

/* Hover Effect on Dots */
.dots label:hover {
    background: #fff;
}

/* Image Transitions Using Radio Buttons */
#img1:checked ~ .m1 {
    margin-left: 0;
}
#img2:checked ~ .m2 {
    margin-left: -100%;
}
#img3:checked ~ .m3 {
    margin-left: -200%;
}
#img4:checked ~ .m4 {
    margin-left: -300%;
}
```
Explanation
Global Styles (* {}): Removes default padding/margins and uses box-sizing: border-box; to include padding inside width calculations.
Body (body {}): Uses display: flex; to center the slider vertically and horizontally. The background color is set to dark blue (rgb(25,12,41)).
Slider (.slider {}): Sets the width to 60% of the screen and hides extra images with overflow: hidden;.
Images (.images img {}): Images are set to full width (width: 100%) and 400px height. A smooth sliding transition is applied using transition: all 0.15s ease;.
Radio Button (.images input {}): Hidden using display: none; since they are used only for selection.
Navigation Dots (.dots label {}): Small circle indicators at the bottom. Clicking them selects a different image.
Sliding Effect (#img1:checked ~ .m1 {}): Moves images left when a radio button is checked:
margin-left: -100% shifts to the next image.
margin-left: -200% shifts to the third image.
margin-left: -300% shifts to the fourth image.
Features
Fully Responsive: Adapts to different screen sizes.
No JavaScript Required: Uses only CSS and HTML.
Smooth Transitions: Uses CSS animations for sliding images.
Navigation Dots: Easy selection using radio buttons.
Possible Improvements
Auto-Sliding: Add JavaScript to change images automatically.
Arrow Navigation: Add previous/next buttons for better control.
More Effects: Use opacity or transform instead of margin-left for smoother transitions.
