---
layout: post
title: About
permalink: /about/
comments: true
---

## Emily Capua

This is me!

![Description of image]({{site.baseurl}}/images/about/EmilyPicture.jpeg)

### Flags:

<style>
    /* Style looks pretty compact, 
       - grid-container and grid-item are referenced the code 
    */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }

    .image-gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        gap: 10px;
        }

    .image-gallery img {
        max-height: 150px;
        object-fit: cover;
        border-radius: 5px;
    }
</style>

<!-- This grid_container class is used by CSS styling and the id is used by JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "0/01/Flag_of_California.svg", "greeting": "California", "description": "2008 - now"},
        {"flag": "ChineseFlag.png", "greeting": "China", "description": "ethnicity"},
        {"flag": "FilipinoFlag.png", "greeting": "Philippines", "description": "ethnicity"},
    ];

    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the greeting
        var greeting = document.createElement("p");
        greeting.textContent = location.greeting;  // extract the greeting

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(greeting);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>


### Contact Info:

Email: emilycapua@gmail.com
Phone: (619)-539-9868
Discord: clover1317
Instagram: [cl0.v3rs](https://www.instagram.com/cl0.v3rs/)

### About Me!

- I am half Filipino and half Chinese.
- I am 17
- My family is composed of my mom, dad, older sister and older brother.
- I have a pet dog too!
- Here's some pictures:

<div class="image-gallery">
  <img src="{{site.baseurl}}/images/about/EmilyPicture1.jpeg" alt="My Photo 1">
  <img src="{{site.baseurl}}/images/about/FilipinoFlag.png" alt="My Photo 2">
  <img src="{{site.baseurl}}/images/about/EmilyPicture3.jpeg" alt="My Photo 3">
  <img src="{{site.baseurl}}/images/about/DashiPicture.jpeg" alt="My Photo 4">
  <img src="{{site.baseurl}}/images/about/ChineseFlag.png" alt="My Photo 5">
</div>

<style>
.image-gallery img {
  width: 100px;
  height: auto;
}
</style>
