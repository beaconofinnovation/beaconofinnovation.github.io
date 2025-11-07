# beaconofinnovation.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Beacon of Innovation</title>
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
font-family: "Segoe UI", Tahoma, sans-serif;
height: 100vh;
display: flex;
justify-content: center;
align-items: center;
background: linear-gradient(135deg, #a7d8ff, #0a3d62);
background-size: 400% 400%;
animation: gradientMove 15s ease infinite;
overflow-x: hidden;
}
@keyframes gradientMove {
0% { background-position:0% 50%; }
50% { background-position:100% 50%; }
100% { background-position:0% 50%; }
}

/* Carousel wrapper */
.carousel-wrapper {
position: relative;
width: 80%;
max-width: 700px;
display: flex;
justify-content: center;
align-items: center;
}

/* Carousel container */
.carousel-container {
width: 100%;
height: 400px;
background: white;
border-radius: 12px;
box-shadow: 0 10px 25px rgba(0,0,0,0.2);
overflow: hidden;
display: flex;
position: relative;
}

/* Slides wrapper */
#slides-wrapper {
display: flex;
width: 200%; /* 2 slides */
height: 100%;
transition: transform 0.5s ease;
}

/* Each slide */
.slide {
flex: 0 0 100%; /* full width of container */
height: 100%;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
text-align: center;
padding: 20px;
box-sizing: border-box;
}

.slide h2 { margin-bottom: 10px; color: #333; }
.slide p { color: #555; line-height: 1.5; max-width: 600px; }

/* Arrows */
.nav-btn {
position: absolute;
top: 50%;
transform: translateY(-50%);
width: 45px;
height: 45px;
border-radius: 50%;
background: rgba(255, 255, 255, 0.7);
color: black;
border: none;
font-size: 22px;
cursor: pointer;
z-index: 20;
}

.nav-btn:hover { background: rgba(255,255,255,1); transform: translateY(-50%) scale(1.1); }
#prev { left: -50px; }
#next { right: -50px; }

/* Apply button */
.apply-btn {
padding: 15px 30px;
border-radius: 10px;
border: none;
background: linear-gradient(to right, #3b82f6, #60a5fa);
color: white;
font-size: 18px;
font-weight: bold;
text-decoration: none;
margin-top: 20px;
}

/* Header */
header {
position: absolute;
top: 10px;
width: 100%;
text-align: center;
color: white;
font-size: 32px;
font-weight: bold;
text-shadow: 2px 2px 5px #000;
}

/* Fixed buttons */
.fixedBtn {
position: fixed;
bottom: 20px;
padding: 10px 15px;
border-radius: 8px;
border: none;
background: #3b82f6;
color: white;
cursor: pointer;
z-index: 10;
}
#aboutBtn { left: 20px; }
#contactBtn { right: 20px; }
#moreBtn { left: 50%; transform: translateX(-50%); }

/* Modals */
.modal {
display: none;
position: fixed;
top: 10%;
left: 50%;
transform: translateX(-50%);
width: 80%;
max-width: 600px;
max-height: 80%;
background: rgba(255,255,255,0.95);
border-radius: 12px;
box-shadow: 0 10px 25px rgba(0,0,0,0.3);
overflow-y: auto;
padding: 20px;
z-index: 999;
}
.modal h2 { margin-top: 0; }
.modal p { line-height: 1.5; }
.closeBtn {
margin-top: 20px;
padding: 10px 15px;
border-radius: 8px;
border: none;
background: #f87171;
color: white;
cursor: pointer;
}
</style>
</head>
<body>

<header>Beacon of Innovation</header>

<div class="carousel-wrapper">
<button id="prev" class="nav-btn">&#10094;</button>

<div class="carousel-container">
<div id="slides-wrapper">
<div class="slide">
<h2>Beacon of Innovation</h2>
<p>
Beacon of Innovation is a program designed<br>
to make learning hands-on and meaningful.<br>
Students work on real-world projects, collaborate<br>
with peers, and explore creative solutions to challenges.<br>
It’s a chance to take ownership of your learning<br>
while building skills that will help you in school, college, and beyond.
</p>
</div>
<div class="slide">
<h2>Join Us!</h2>
<a href="https://forms.cloud.microsoft/r/i8SdrJV95t" target="_blank" class="apply-btn">Apply Now</a>
</div>
</div>
</div>

<button id="next" class="nav-btn">&#10095;</button>
</div>

<!-- Fixed buttons -->
<button id="aboutBtn" class="fixedBtn">About</button>
<button id="contactBtn" class="fixedBtn">Contact</button>
<button id="moreBtn" class="fixedBtn">More on Beacon of Innovation</button>

<!-- Modals -->
<div id="aboutModal" class="modal">
<h2>About Vision.AZPS</h2>
<p><strong>Vision:</strong> AZPS is a community of lifelong learners that strives for academic excellence, prepares students for global challenges, and maintains cultural identity.</p>
<p><strong>Core Values:</strong> Respect - Academic Honesty - Responsibility - Cooperation - Tolerance.</p>
<p><strong>Learning:</strong> Learning is a process by which individuals acquire knowledge and skills through researching, experimenting, and problem-solving. Teachers act as facilitators by providing learners a degree of voice and choice in their own learning, hands-on experiences requiring high-level thinking skills, and varied assessment practices where feedback is directly linked to performance level.</p>
<button class="closeBtn">Back</button>
</div>

<div id="contactModal" class="modal">
<h2>Contact Us</h2>
<p>Email: BeaconofInnovation@gmail.com</p>
<p>Phone: 0502065383</p>
<button class="closeBtn">Back</button>
</div>

<script>
// Carousel
const slidesWrapper = document.getElementById('slides-wrapper');
const slides = document.querySelectorAll('.slide');
let currentIndex = 0;

function showSlide(index) {
slidesWrapper.style.transform = `translateX(-${index * 100}%)`; // each slide = 100%
}

document.getElementById('prev').onclick = () => {
currentIndex = (currentIndex === 0) ? slides.length - 1 : currentIndex - 1;
showSlide(currentIndex);
}

document.getElementById('next').onclick = () => {
currentIndex = (currentIndex === slides.length - 1) ? 0 : currentIndex + 1;
showSlide(currentIndex);
}

// Modals
const aboutBtn = document.getElementById('aboutBtn');
const contactBtn = document.getElementById('contactBtn');
const moreBtn = document.getElementById('moreBtn');
const aboutModal = document.getElementById('aboutModal');
const contactModal = document.getElementById('contactModal');
const closeButtons = document.querySelectorAll('.closeBtn');

aboutBtn.onclick = () => { aboutModal.style.display = 'block'; }
contactBtn.onclick = () => { contactModal.style.display = 'block'; }
moreBtn.onclick = () => { window.open('https://www.canva.com/design/DAG2WEMTVS0/CJrO3jQd01EY0zp8NBFq0A/view'); }

closeButtons.forEach(btn => {
btn.onclick = () => {
aboutModal.style.display = 'none';
contactModal.style.display = 'none';
}
});

window.onclick = function(event) {
if (event.target === aboutModal) aboutModal.style.display = "none";
if (event.target === contactModal) contactModal.style.display = "none";
}
</script>

</body>
</html>
