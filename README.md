# New-project-
<div class="slideshow-container fade">
<div class="Containers">
    <div class="MessageInfo">1 / 3</div>
    <img src="image1.jpg" style="width:100%">
    <div class="Info">First caption</div>
  </div>

  <div class="Containers">
    <div class="MessageInfo">2 / 3</div>
    <img src="image2.jpg" style="width:100%">
    <div class="Info">Second Caption</div>
  </div>

  <div class="Containers">
    <div class="MessageInfo">3 / 3</div>
    <img src="image3.jpg" style="width:100%">
    <div class="Info">Third Caption</div>
  </div>

  <!-- Back and forward buttons -->
  <a class="Back" onclick="plusSlides(-1)">&#10094;</a>
  <a class="forward" onclick="plusSlides(1)">&#10095;</a>
</div>
<br>

<!-- The circles/dots -->
<div style="text-align:center">
  <span class="dots" onclick="currentSlide(1)"></span>
  <span class="dots" onclick="currentSlide(2)"></span>
  <span class="dots" onclick="currentSlide(3)"></span>
<div>
* {box-sizing:border-box}
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Make the images invisible by default */
.Containers {
  display: none;
}

/* forward & Back buttons */
.Back, .forward {
  cursor: pointer;
  position: absolute;
  top: 48%;
  width: auto;
  margin-top: -23px;
  padding: 17px;
  color: grey;
  font-weight: bold;
  font-size: 19px;
  transition: 0.4s ease;
  border-radius: 0 5px 5px 0;
  user-select: none;
}

/* Place the "forward button" to the right */
.forward {
  right: 0;
  border-radius: 4px 0 0 4px;
}

/*when the user hovers,add a black background with some little opacity */
.Back:hover, .forward:hover {
  background-color: rgba(0,0,0,0.8);
}

/* Caption Info */
.Info {
  color: #e3e3e3;
  font-size: 16px;
  padding: 10px 14px;
  position: absolute;
  bottom: 10px;
  width: 100%;
  text-align: center;
}

/* Worknumbering (1/3 etc) */
.MessageInfo {
  color: #f2f2f3;
  font-size: 14px;
  padding: 10px 14px;
  position: absolute;
  top: 0;
}

/* The circles or bullets and indicators */
.dots {
  cursor: pointer;
  height: 16px;
  width: 16px;
  margin: 0 3px;
  background-color: #acc;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.5s ease;
}

.enable, .dots:hover {
  background-color: #717161;
}

/* Faint animation */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.4s;
  animation-name: fade;
  animation-duration: 1.4s;
}

@-webkit-keyframes fade {
  from {opacity: .5}
  to {opacity: 2}
}

@keyframes fade {
  from {opacity: .5}
  to {opacity: 2}

var slidePosition = 1
SlideShow(slidePosition);

// forward/Back controls
function plusSlides(n) {
  SlideShow(slidePosition += n);
}

//  images controls
function currentSlide(n) {
  SlideShow(slidePosition = n);
}

function SlideShow(n) {
  var i;
  var slides = document.getElementsByClassName("Containers");
  var circles = document.getElementsByClassName("dots");
  if (n > slides.length) {slidePosition = 1}
  if (n < 1) {slidePosition = slides.length}
  for (i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
  }
  for (i = 0; i < circles.length; i++) {
      circles[i].className = circles[i].className.replace(" enable", "");
  }
  slides[slidePosition-1].style.display = "block";
 circles[slidePosition-1].className
}
var slidePosition = 0;
SlideShow();

function SlideShow() {
  var i;
  var slides = document.getElementsByClassName("Containers");
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }
  slidePosition++;
  if (slidePosition > slides.length) {slidePosition = 1}
  slides[slidePosition-1].style.display = "block";
  
