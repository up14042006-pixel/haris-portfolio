<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Haris Portfolio</title>

<style>

/* ===== GLOBAL ===== */
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
    scroll-behavior:smooth;
}

body{
    background:#f3f4f6;
    color:#111;
    transition:0.4s;
}

body.dark{
    background:#0f172a;
    color:#f1f5f9;
}

/* ===== HEADER ===== */
header{
    background:linear-gradient(to right,#1e3a8a,#0f172a);
    color:white;
    padding:80px 20px;
    text-align:center;
}

header h1{
    font-size:40px;
}

header p{
    margin-top:10px;
    font-size:18px;
}

/* ===== NAV ===== */
nav{
    position:sticky;
    top:0;
    background:#111827;
    padding:15px;
    display:flex;
    justify-content:center;
    gap:30px;
    z-index:1000;
}

nav a{
    color:white;
    text-decoration:none;
    font-weight:bold;
    transition:0.3s;
}

nav a:hover{
    color:#38bdf8;
}

.toggle-btn{
    position:absolute;
    right:20px;
    cursor:pointer;
    color:white;
}

/* ===== SECTION ===== */
section{
    padding:80px 20px;
    text-align:center;
    opacity:0;
    transform:translateY(40px);
    transition:1s;
}

section.show{
    opacity:1;
    transform:translateY(0);
}

/* ===== SKILLS ===== */
.skills{
    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    gap:20px;
}

.skill-box{
    background:white;
    padding:20px;
    border-radius:10px;
    width:150px;
    box-shadow:0 10px 20px rgba(0,0,0,0.1);
    transition:0.4s;
}

body.dark .skill-box{
    background:#1e293b;
}

.skill-box:hover{
    transform:translateY(-10px);
}

/* ===== PROJECTS ===== */
.project-card{
    background:white;
    margin:20px auto;
    padding:20px;
    border-radius:10px;
    max-width:400px;
    box-shadow:0 10px 20px rgba(0,0,0,0.1);
    transition:0.4s;
}

body.dark .project-card{
    background:#1e293b;
}

.project-card:hover{
    transform:scale(1.05);
}

/* ===== CONTACT ===== */
form{
    max-width:400px;
    margin:20px auto;
}

input,textarea{
    width:100%;
    padding:10px;
    margin-bottom:15px;
    border-radius:6px;
    border:1px solid #ccc;
}

button{
    padding:10px 20px;
    border:none;
    background:#1e3a8a;
    color:white;
    border-radius:6px;
    cursor:pointer;
    transition:0.3s;
}

button:hover{
    background:#0f172a;
}

/* ===== FOOTER ===== */
footer{
    background:#111827;
    color:white;
    text-align:center;
    padding:20px;
}

</style>
</head>

<body>

<nav>
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
    <span class="toggle-btn" onclick="toggleMode()">🌙</span>
</nav>

<header>
    <h1>Hi, I'm Haris 👋</h1>
    <p id="typing"></p>
</header>

<section id="about">
    <h2>About Me</h2>
    <p>I am learning Web Development and building modern websites using HTML, CSS and JavaScript.</p>
</section>

<section id="skills">
    <h2>My Skills</h2>
    <div class="skills">
        <div class="skill-box">HTML</div>
        <div class="skill-box">CSS</div>
        <div class="skill-box">JavaScript</div>
    </div>
</section>

<section id="projects">
    <h2>My Projects</h2>
    <div class="project-card">
        <h3>First HTML Website</h3>
        <p>My beginner website project.</p>
    </div>
    <div class="project-card">
        <h3>Portfolio Website</h3>
        <p>This professional animated portfolio.</p>
    </div>
</section>

<section id="contact">
    <h2>Contact Me</h2>
    <form onsubmit="showMessage(event)">
        <input type="text" placeholder="Your Name" required>
        <input type="email" placeholder="Your Email" required>
        <textarea placeholder="Your Message" required></textarea>
        <button type="submit">Send Message</button>
    </form>
    <p id="msg"></p>
</section>

<footer>
    © 2026 Haris Portfolio | Made with ❤️
</footer>

<script>

/* ===== DARK MODE ===== */
function toggleMode(){
    document.body.classList.toggle("dark");
}

/* ===== TYPING EFFECT ===== */
const text = "Front-End Web Developer";
let i = 0;

function typing(){
    if(i < text.length){
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typing,100);
    }
}
typing();

/* ===== SCROLL ANIMATION ===== */
const sections = document.querySelectorAll("section");

window.addEventListener("scroll",()=>{
    sections.forEach(sec=>{
        const top = window.scrollY;
        const offset = sec.offsetTop - 400;
        if(top > offset){
            sec.classList.add("show");
        }
    });
});

/* ===== CONTACT MESSAGE ===== */
function showMessage(e){
    e.preventDefault();
    document.getElementById("msg").innerHTML = "Message Sent Successfully!";
}

</script>

</body>
</html>
