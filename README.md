# File Upload Component

This repository contains code for a simple file upload component. Users can either drag and drop an image file or browse their system to upload an image.

## Usage

To use this component, simply include the HTML code provided in your project. You may need to adjust the paths to the image files based on your project structure.

```html
<div class="file-upload">
  <div class="file-wrap">
    <input type="file" name="upload" id="fileupload">
    <div class="custom-upload-design">
        <div class="upload-icon">
          <img src="assets/images/system-regular-49-upload-file.gif" alt="" >
        </div>
        <div class="upload-text">Drag and drop <br> an images, or <span>Browse</span></div>
    </div>
  </div>
</div>

# CSS Styles for File Upload Component

This repository contains CSS styles for a simple file upload component. These styles define the appearance and behavior of the file upload component.

## Usage

To use these styles, include the provided CSS code in your project. You may need to adjust class names and paths to images based on your project structure.

```css
/* Paste provided CSS here */
* {
    box-sizing: border-box;
}
body {
    margin: 0px;
    padding:0px;
    background-color: #F1F5F8;
    font-family: Arial, Helvetica, sans-serif;
}
.ignore-container {
    width: 100%;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}
.file-upload {
    max-width: 450px;
    padding:50px;
    width: 100%;
    position: relative;
    border-radius: 12px;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0,0,0,0.05);
}
.file-wrap {
    border: 2px dashed #F13218;
    border-radius: 12px;
    position: relative;
    transition: all 0.5s ease;
    transform: scale(1);
}
.file-wrap.dragging {
    transform: scale(1.1);
}
.file-wrap input[type="file"] {
    position: absolute;
    left: 0px;
    right: 0px;
    top: 0px;
    bottom: 0px;
    opacity: 0;
    cursor: pointer;
    z-index: 2;
}
.custom-upload-design {
    padding:50px 30px;
    min-height: 250px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
.upload-text {
    font-size: 24px;
    text-align: center;
}
.upload-text span {
    color: #F13218;
}
.upload-icon {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #F13218;
    margin-bottom: 15px;
    transform: scale(1);
    transition: transform 0.5s ease-in-out;
}
.upload-icon img {
    max-width:20px;
}
.dropped .upload-text {
    display: none;
}
.dropped .upload-icon {
    transform: scale(2.8);
    opacity: 1;
    transition: all 0.5s ease-in-out;
    animation: bounce 1s .5s;
    
}
.animate .upload-icon {
    opacity: 0;
}
.dropped .upload-icon img {
    opacity: 0;
}
.file-wrap.dropped {
    border-color: transparent;
}
.after-file-upload {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.animated-line {
    stroke: #07da38;
    stroke-width: 20;
    fill: transparent;
     animation: progressAnimation 2s linear; 
    position: relative;
    top: -6px;
    z-index: 1;
}
.animated-line-2 {
    stroke: #ffebe8;
    stroke-width: 20;
    fill: transparent;
    position: absolute;
    margin: auto;
    top: 19px;
}

@keyframes progressAnimation {
    0% {
        stroke-dasharray: 0, 565; 
        stroke:#f13218;
    }
    
    100% {
        stroke-dasharray: 565; 
        stroke:#07da38;
    }
}
.after-file-upload > div {
    position: absolute;
    left: 0px;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
    max-width: 100px;
    margin: 0 auto;
}
.uploaded .after-file-upload  {
    transform: scale(0.5);
    top: -10px;
    transition: all 0.5s ease;
}
.tick-line {
    width: 100px;
    height: 100px;
}
.path {
    stroke-dasharray: 1000;
    stroke-dashoffset: 0;
}
.path.check {
    stroke-dashoffset: -100;
    -webkit-animation: dash-check 0.9s 0.35s ease-in-out forwards;
    animation: dash-check 0.9s 0.35s ease-in-out forwards;
}
@-webkit-keyframes dash-check {
    0% {
      stroke-dashoffset: -100;
    }
    100% {
      stroke-dashoffset: 900;
    }
}
@keyframes dash-check {
    0% {
      stroke-dashoffset: -100;
    }
    100% {
      stroke-dashoffset: 900;
    }
}

.text-uploaded {
    position: absolute;
    bottom: -30px;
    font-size: 32px;
    left: 0;
    right: 0;
    text-align: center;
}


# JavaScript Code for File Upload Component

This repository contains JavaScript code for a simple file upload component. This code handles the drag and drop functionality and the file upload animation.

## Usage

To use this JavaScript code, include it in your project. You can place it within a `<script>` tag in your HTML file or in a separate JavaScript file and link it to your HTML.

```javascript
/* Paste provided JavaScript here */

_animateCircle=`<svg class="animated-line" width="200" height="200" xmlns="http://www.w3.org/2000/svg"><path d="M 100 100 m 0 -90 a 90 90 0 1 1 0 180 a 90 90 0 0 1 0 -180" id="line" stroke-linecap="round"></path>
</svg> <svg class="animated-line-2" width="200" height="200" xmlns="http://www.w3.org/2000/svg"><path d="M 100 100 m 0 -90 a 90 90 0 1 1 0 180 a 90 90 0 0 1 0 -180" id="line" stroke-linecap="round"></path>
</svg>`,_animatetick=`<svg class="tick-line" version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 130.2 130.2"><polyline class="path check" fill="none" stroke="#07da38" stroke-width="15" stroke-linecap="round" stroke-miterlimit="10" points="100.2,40.2 51.5,88.8 29.8,67.5 "/>
</svg>`;const div=document.createElement("div");div.classList.add("after-file-upload");var upload=document.querySelector("#fileupload"),parent_ele=document.querySelector(".file-wrap"),text_upload=document.querySelector(".custom-upload-design");parent_ele.appendChild(div);var after_upload=document.querySelector(".after-file-upload");function dropping(){parent_ele.classList.remove("dragging"),parent_ele.classList.add("dropped"),setTimeout(function(){after_upload.innerHTML=_animateCircle,parent_ele.classList.add("animate")},800),setTimeout(function(){let e=document.createElement("div");e.innerHTML=_animatetick,after_upload.appendChild(e)},3e3),setTimeout(function(){parent_ele.classList.add("uploaded");let e=document.createElement("span");e.innerHTML="Uploaded",e.classList.add("text-uploaded"),after_upload.appendChild(e)},3500)}upload.addEventListener("dragover",function(e){parent_ele.classList.remove("animate"),parent_ele.classList.remove("dropped"),parent_ele.classList.remove("uploaded"),parent_ele.classList.add("dragging"),after_upload.innerHTML=""},!1),upload.addEventListener("drop",function(e){dropping()},!1),upload.addEventListener("change",function(e){dropping()});
