# Carousel 

## Overview
This project is a simple image carousel (slider) built using HTML and CSS. It allows users to navigate through multiple images using radio buttons and styled navigation dots.

## Project Structure
---
```
/carousel-slider
├── index.html # Main HTML file
├── style.css # CSS for styling
├── 1.jpg # Image 1
├── 2.jpg # Image 2 
├── 3.jpg # Image 3 
├── 4.jpg # Image 4
```
---

## 1. `index.html` (HTML Structure)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carousel</title>
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
<input type="radio">:

Radio buttons allow users to switch between images.
name="slide" ensures that only one radio button can be selected at a time.
id="img1" links each radio button to an image.
The checked attribute on img1 sets it as the default image.


Images are linked with classes (.m1, .m2, .m3, .m4) for styling and transition effects.
Navigation Dots (<label> for radio buttons)

Labels are used as interactive dots at the bottom. Clicking on a dot changes the displayed image.


## 2. style.css (CSS Styling)
   
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
    width: 400%;
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

## Explanation:
Global Styles (* {}):
Removes default padding and margins, and uses box-sizing: border-box; to include padding inside width calculations.

Body (body {}):
Centers the carousel slider both vertically and horizontally using Flexbox.
Sets the background color to dark blue (rgb(25,12,41)).

Slider Container (.slider {}):
Sets the width of the slider to 60% of the screen and hides any extra images using overflow: hidden;.

Images (.images img {}):
Makes images fill the width of the container (width: 400%) and sets their height to 400px.
Applies a smooth transition effect for sliding.

Radio Buttons (.images input {}):
Hides the radio buttons since they are only used for selection and not for direct interaction with users.

Navigation Dots (.dots label {}):
Displays circular dots below the images, which act as selectors.
Provides a hover effect that changes the background color to white when hovered.

Image Transitions (#img1:checked ~ .m1 {}):
Uses radio button states to shift images to the left when a button is selected

margin-left: -100% moves to the second image.

margin-left: -200% moves to the third image.

margin-left: -300% moves to the fourth image.

## Features
Fully Responsive: The slider adapts to different screen sizes.

No JavaScript Required: The carousel uses only CSS and HTML to create the sliding effect.

Smooth Transitions: The images slide with a smooth transition effect using CSS.

Navigation Dots: Allows easy image selection using interactive dots.

## Possible Improvements
Auto-Sliding: Add JavaScript to automatically change images after a certain interval.

Arrow Navigation: Implement previous/next buttons for better control over the slider.

More Effects: Explore using opacity or transform for smoother image transitions instead of margin-left.

Auto-Sliding: Add JavaScript to automatically change images after a certain interval.

Arrow Navigation: Implement previous/next buttons for better control over the slider.

More Effects: Explore using opacity or transform for smoother image transitions instead of margin-left.

## Conclusion
This image carousel project is a simple yet effective demonstration of creating an interactive slider using only HTML and CSS. It provides a smooth user experience with easy navigation via radio buttons and styled navigation dots. The project is responsive, adaptable to various screen sizes, and doesn't require any JavaScript for its core functionality, making it lightweight and easy to integrate into websites. With room for further improvements, such as adding auto-sliding functionality or arrow navigation, this carousel can be enhanced to fit more complex requirements.
