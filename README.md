
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SMARTELAM | 3D Developer Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>

<style>
:root {
  --bg: #080511;
  --panel: rgba(27, 12, 43, .65);
  --pink: #ff29d9;
  --purple: #9b5cff;
  --cyan: #54e9ff;
  --white: #f9f4ff;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  background: var(--bg);
  color: var(--white);
  font-family: 'Poppins', sans-serif;
  overflow-x: hidden;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  z-index: -1;
  background:
    radial-gradient(circle at 20% 30%, #6b1a9d33, transparent 40%),
    radial-gradient(circle at 80% 70%, #ff149333, transparent 40%);
}

#scene {
  position: fixed;
  inset: 0;
  z-index: -2;
  pointer-events: none;
}

a {
  color: inherit;
  text-decoration: none;
}

.container {
  width: min(1150px, 90%);
  margin: auto;
}

nav {
  position: fixed;
  top: 18px;
  left: 50%;
  transform: translateX(-50%);
  width: min(1100px, 92%);
  padding: 16px 25px;
  z-index: 100;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(16, 8, 29, .7);
  backdrop-filter: blur(20px);
  border: 1px solid #ffffff20;
  border-radius: 18px;
}

.logo {
  font-family: Orbitron;
  font-size: 19px;
  font-weight: 900;
  color: var(--pink);
  text-shadow: 0 0 15px var(--pink);
}

.nav-links {
  display: flex;
  gap: 28px;
  list-style: none;
}

.nav-links a {
  font-size: 13px;
  transition: .3s;
}

.nav-links a:hover {
  color: var(--pink);
  text-shadow: 0 0 15px var(--pink);
}

.menu {
  display: none;
  font-size: 25px;
  cursor: pointer;
}

.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  padding-top: 100px;
}

.hero-content {
  max-width: 750px;
  position: relative;
  z-index: 2;
}

.tag {
  display: inline-block;
  padding: 9px 17px;
  border: 1px solid #ff29d966;
  background: #ff29d911;
  border-radius: 30px;
  color: var(--pink);
  font-size: 12px;
  letter-spacing: 2px;
  margin-bottom: 25px;
}

h1 {
  font-family: Orbitron;
  font-size: clamp(40px, 8vw, 90px);
  line-height: 1.15;
  font-weight: 900;
}

.gradient {
  background: linear-gradient(90deg, #ff29d9, #9b5cff, #54e9ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.hero p {
  color: #b9aacb;
  font-size: 16px;
  line-height: 1.9;
  margin: 25px 0;
  max-width: 570px;
}

.typing {
  color: var(--cyan);
  font-size: 18px;
  min-height: 35px;
}

.buttons {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
  margin-top: 30px;
}

.btn {
  padding: 14px 26px;
  border-radius: 10px;
  font-weight: 600;
  font-size: 13px;
  transition: .35s;
  border: 1px solid var(--pink);
  display: inline-block;
}

.btn-primary {
  background: linear-gradient(100deg, #9b5cff, #ff29d9);
  border: none;
  box-shadow: 0 0 25px #ff29d944;
}

.btn:hover {
  transform: translateY(-5px);
  box-shadow: 0 0 30px #ff29d988;
}

.section {
  padding: 110px 0;
}

.section-title {
  text-align: center;
  font-family: Orbitron;
  font-size: clamp(27px, 5vw, 43px);
  margin-bottom: 15px;
}

.section-desc {
  text-align: center;
  color: #aa9bbd;
  margin-bottom: 55px;
}

.glass {
  background: var(--panel);
  border: 1px solid #ffffff1b;
  backdrop-filter: blur(20px);
  border-radius: 20px;
  box-shadow: 0 15px 50px #0005;
}

.about-card {
  padding: 40px;
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  gap: 35px;
  align-items: center;
}

.about-card h3 {
  font-family: Orbitron;
  color: var(--pink);
  margin-bottom: 20px;
}

.about-card p {
  color: #b9aacb;
  line-height: 2;
  font-size: 14px;
}

.stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.stat {
  text-align: center;
  padding: 24px 10px;
  border: 1px solid #a75cff44;
  border-radius: 14px;
  background: #9b5cff0d;
}

.stat h2 {
  font-family: Orbitron;
  color: var(--pink);
  font-size: 27px;
}

.stat p {
  font-size: 11px;
  margin-top: 8px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 18px;
}

.skill {
  text-align: center;
  padding: 30px 12px;
  transition: .4s;
  transform-style: preserve-3d;
}

.skill:hover {
  transform: perspective(600px) rotateX(8deg) rotateY(-8deg) translateY(-10px);
  border-color: var(--pink);
  box-shadow: 0 0 25px #ff29d933;
}

.skill .icon {
  font-size: 35px;
  margin-bottom: 15px;
}

.skill h4 {
  font-size: 13px;
  color: #e8d9ff;
}

.projects {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 25px;
}

.project {
  padding: 27px;
  transition: .4s;
  transform-style: preserve-3d;
  position: relative;
  overflow: hidden;
}

.project:hover {
  border-color: var(--pink);
  box-shadow: 0 0 30px #a855f744;
}

.project-image {
  height: 150px;
  border-radius: 13px;
  display: grid;
  place-items: center;
  font-size: 65px;
  margin-bottom: 25px;
  background: linear-gradient(135deg, #40105e, #a91b86, #1c1651);
}

.project h3 {
  font-family: Orbitron;
  font-size: 17px;
  margin-bottom: 12px;
}

.project p {
  font-size: 13px;
  color: #ad9cbd;
  line-height: 1.8;
}

.project a {
  display: inline-block;
  margin-top: 22px;
  color: var(--cyan);
  font-size: 13px;
}

.contact-card {
  text-align: center;
  padding: 55px 25px;
}

.contact-card p {
  color: #ad9cbd;
  margin: 20px auto;
  max-width: 550px;
  line-height: 1.8;
}

.socials {
  display: flex;
  justify-content: center;
  gap: 15px;
  flex-wrap: wrap;
  margin-top: 30px;
}

.socials a {
  padding: 13px 20px;
  border-radius: 10px;
  border: 1px solid #a855f766;
  transition: .3s;
  font-size: 13px;
}

.socials a:hover {
  background: #a855f733;
  box-shadow: 0 0 20px #ff29d955;
  transform: translateY(-5px);
}

footer {
  text-align: center;
  padding: 30px;
  color: #887899;
  font-size: 12px;
  border-top: 1px solid #ffffff12;
}

.reveal {
  opacity: 0;
  transform: translateY(45px);
}

@media(max-width: 700px) {
  .nav-links {
    display: none;
    position: absolute;
    top: 70px;
    left: 0;
    right: 0;
    flex-direction: column;
    padding: 25px;
    background: #150b24;
    border: 1px solid #ffffff22;
    border-radius: 15px;
  }

  .nav-links.active {
    display: flex;
  }

  .menu {
    display: block;
  }

  .about-card {
    grid-template-columns: 1fr;
    padding: 25px;
  }

  .hero {
    min-height: 90vh;
  }

  .section {
    padding: 75px 0;
  }
}

@media(prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    scroll-behavior: auto !important;
    transition-duration: .01ms !important;
  }
}
</style>
</head>

<body>

<canvas id="scene"></canvas>

<nav>
  <a href="#home" class="logo">SMARTELAM.</a>

  <ul class="nav-links" id="navLinks">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>

  <div class="menu" id="menu">☰</div>
</nav>

<!-- HERO -->

<header class="hero container" id="home">
  <div class="hero-content">

    <span class="tag">✦ AVAILABLE FOR CREATIVE PROJECTS</span>

    <h1>
      HELLO,<br>
      I'M <span class="gradient">SMARTELAM</span>
    </h1>

    <div class="typing">
      <span id="typed"></span>
    </div>

    <p>
      I create beautiful digital experiences by combining
      modern technology, creative thinking, and futuristic
      design. Welcome to my digital universe.
    </p>

    <div class="buttons">
      <a href="#projects" class="btn btn-primary">EXPLORE PROJECTS ↗</a>
      <a href="#contact" class="btn">CONTACT ME</a>
    </div>

  </div>
</header>

<!-- ABOUT -->

<section class="section container reveal" id="about">

  <h2 class="section-title">ABOUT <span class="gradient">ME</span></h2>
  <p class="section-desc">The person behind the code.</p>

  <div class="about-card glass">

    <div>
      <h3>CREATIVE DEVELOPER</h3>
      <p>
        Hey! I'm Smartelam, a Full Stack Developer passionate
        about building modern web applications and amazing
        user experiences.

        I enjoy exploring new technologies, designing beautiful
        interfaces, and turning complex ideas into simple,
        elegant digital solutions.
      </p>
    </div>

    <div class="stats">
      <div class="stat">
        <h2>01+</h2>
        <p>DEVELOPER JOURNEY</p>
      </div>
      <div class="stat">
        <h2>∞</h2>
        <p>CREATIVITY</p>
      </div>
      <div class="stat">
        <h2>24/7</h2>
        <p>LEARNING MINDSET</p>
      </div>
      <div class="stat">
        <h2>100%</h2>
        <p>PASSION</p>
      </div>
    </div>

  </div>
</section>

<!-- SKILLS -->

<section class="section container reveal" id="skills">

  <h2 class="section-title">MY <span class="gradient">ARSENAL</span></h2>
  <p class="section-desc">Technologies I work with.</p>

  <div class="skills-grid">

    <div class="skill glass"><div class="icon">🌐</div><h4>HTML5</h4></div>
    <div class="skill glass"><div class="icon">🎨</div><h4>CSS3</h4></div>
    <div class="skill glass"><div class="icon">⚡</div><h4>JavaScript</h4></div>
    <div class="skill glass"><div class="icon">⚛️</div><h4>React</h4></div>
    <div class="skill glass"><div class="icon">🟢</div><h4>Node.js</h4></div>
    <div class="skill glass"><div class="icon">🐍</div><h4>Python</h4></div>
    <div class="skill glass"><div class="icon">🍃</div><h4>MongoDB</h4></div>
    <div class="skill glass"><div class="icon">🐬</div><h4>MySQL</h4></div>
    <div class="skill glass"><div class="icon">🔧</div><h4>Git</h4></div>
    <div class="skill glass"><div class="icon">🐙</div><h4>GitHub</h4></div>

  </div>
</section>

<!-- PROJECTS -->

<section class="section container reveal" id="projects">

  <h2 class="section-title">FEATURED <span class="gradient">PROJECTS</span></h2>
  <p class="section-desc">A showcase of my creative universe.</p>

  <div class="projects">

    <article class="project glass">
      <div class="project-image">🌌</div>
      <h3>3D PORTFOLIO</h3>
      <p>A futuristic interactive developer portfolio with 3D animations and neon effects.</p>
      <a href="https://github.com/smartelam12-hub" target="_blank">VIEW PROJECT ↗</a>
    </article>

    <article class="project glass">
      <div class="project-image">💻</div>
      <h3>WEB APPLICATION</h3>
      <p>A modern responsive application designed with clean UI and smooth user experience.</p>
      <a href="https://github.com/smartelam12-hub" target="_blank">VIEW PROJECT ↗</a>
    </article>

    <article class="project glass">
      <div class="project-image">🚀</div>
      <h3>CREATIVE PROJECT</h3>
      <p>A creative digital experiment built using modern development technologies.</p>
      <a href="https://github.com/smartelam12-hub" target="_blank">VIEW PROJECT ↗</a>
    </article>

  </div>
</section>

<!-- CONTACT -->

<section class="section container reveal" id="contact">

  <div class="contact-card glass">

    <span class="tag">✦ LET'S CONNECT</span>

    <h2 class="section-title">
      LET'S BUILD THE <span class="gradient">FUTURE</span>
    </h2>

    <p>
      Have an interesting idea or project?
      Let's connect and create something extraordinary together.
    </p>

    <div class="socials">
      <a href="https://github.com/smartelam12-hub" target="_blank">GITHUB ↗</a>
      <a href="mailto:YOUR_EMAIL@gmail.com">EMAIL ↗</a>
      <a href="https://linkedin.com/in/YOUR_LINKEDIN" target="_blank">LINKEDIN ↗</a>
    </div>

  </div>
</section>

<footer>
  © 2026 SMARTELAM12-HUB | DESIGNED WITH 💜 AND CODE
</footer>

<!-- THREE.JS 3D ENGINE -->

<script type="module">
import * as THREE from
'https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.module.js';

const canvas = document.querySelector('#scene');

const scene = new THREE.Scene();
scene.fog = new THREE.FogExp2(0x080511, 0.035);

const camera = new THREE.PerspectiveCamera(
  65,
  window.innerWidth / window.innerHeight,
  0.1,
  100
);

camera.position.z = 9;

const renderer = new THREE.WebGLRenderer({
  canvas,
  alpha: true,
  antialias: true
});

renderer.setSize(window.innerWidth, window.innerHeight);
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

scene.add(new THREE.AmbientLight(0xffffff, 1.3));

const pinkLight = new THREE.PointLight(0xff29d9, 30, 30);
pinkLight.position.set(4, 3, 5);
scene.add(pinkLight);

const purpleLight = new THREE.PointLight(0x8844ff, 35, 30);
purpleLight.position.set(-4, -3, 4);
scene.add(purpleLight);

// Main floating 3D object

const geometry = new THREE.TorusKnotGeometry(1.5, 0.38, 180, 24);

const material = new THREE.MeshPhysicalMaterial({
  color: 0xa64cff,
  metalness: 0.75,
  roughness: 0.18,
  emissive: 0x280044,
  emissiveIntensity: 1.1,
  wireframe: false
});

const knot = new THREE.Mesh(geometry, material);
knot.position.set(4.2, 0.1, -1.5);
scene.add(knot);

// Wireframe outer shell

const shell = new THREE.Mesh(
  new THREE.IcosahedronGeometry(2.3, 2),
  new THREE.MeshBasicMaterial({
    color: 0xff29d9,
    wireframe: true,
    transparent: true,
    opacity: 0.16
  })
);

shell.position.copy(knot.position);
scene.add(shell);

// Floating particles

const count = 1600;
const positions = new Float32Array(count * 3);

for (let i = 0; i < count * 3; i++) {
  positions[i] = (Math.random() - 0.5) * 35;
}

const particleGeometry = new THREE.BufferGeometry();
particleGeometry.setAttribute(
  'position',
  new THREE.BufferAttribute(positions, 3)
);

const particleMaterial = new THREE.PointsMaterial({
  color: 0xff55ee,
  size: 0.035,
  transparent: true,
  opacity: 0.8
});

const particles = new THREE.Points(
  particleGeometry,
  particleMaterial
);

scene.add(particles);

// Floating mini shapes

const objects = [];

for (let i = 0; i < 12; i++) {
  const mesh = new THREE.Mesh(
    new THREE.OctahedronGeometry(
      0.15 + Math.random() * 0.2
    ),
    new THREE.MeshStandardMaterial({
      color: i % 2 ? 0xff29d9 : 0x8955ff,
      emissive: i % 2 ? 0x440022 : 0x220044,
      wireframe: true
    })
  );

  mesh.position.set(
    (Math.random() - 0.5) * 17,
    (Math.random() - 0.5) * 12,
    (Math.random() - 0.5) * 8
  );

  objects.push(mesh);
  scene.add(mesh);
}

// Mouse interaction

let mouseX = 0;
let mouseY = 0;

window.addEventListener('pointermove', (event) => {
  mouseX = (event.clientX / window.innerWidth - 0.5);
  mouseY = (event.clientY / window.innerHeight - 0.5);
});

let clock = new THREE.Clock();

function animate() {
  requestAnimationFrame(animate);

  const time = clock.getElapsedTime();

  knot.rotation.x = time * 0.17 + mouseY * 0.4;
  knot.rotation.y = time * 0.24 + mouseX * 0.4;

  shell.rotation.x = -time * 0.08;
  shell.rotation.y = time * 0.11;

  particles.rotation.y = time * 0.008;

  objects.forEach((obj, i) => {
    obj.rotation.x += 0.005;
    obj.rotation.y += 0.008;
    obj.position.y += Math.sin(time + i) * 0.001;
  });

  camera.position.x += (mouseX * 0.7 - camera.position.x) * 0.025;
  camera.position.y += (-mouseY * 0.7 - camera.position.y) * 0.025;

  camera.lookAt(0, 0, 0);

  renderer.render(scene, camera);
}

animate();

window.addEventListener('resize', () => {
  camera.aspect = window.innerWidth / window.innerHeight;
  camera.updateProjectionMatrix();

  renderer.setSize(window.innerWidth, window.innerHeight);
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
});
</script>

<!-- UI ANIMATIONS -->

<script>
gsap.registerPlugin(ScrollTrigger);

// Hero entrance
gsap.from(".hero-content > *", {
  y: 45,
  opacity: 0,
  duration: 1.1,
  stagger: 0.18,
  ease: "power3.out"
});

// Section reveal
gsap.utils.toArray(".reveal").forEach(section => {
  gsap.to(section, {
    opacity: 1,
    y: 0,
    duration: 1,
    ease: "power3.out",
    scrollTrigger: {
      trigger: section,
      start: "top 85%"
    }
  });
});

// Typing animation
const words = [
  "FULL STACK DEVELOPER",
  "CREATIVE CODER",
  "UI / UX ENTHUSIAST",
  "TECH EXPLORER"
];

let wordIndex = 0;
let charIndex = 0;
let deleting = false;

function type() {
  const current = words[wordIndex];
  const element = document.getElementById("typed");

  element.textContent = current.substring(0, charIndex);

  if (!deleting) {
    charIndex++;

    if (charIndex > current.length) {
      deleting = true;
      setTimeout(type, 1200);
      return;
    }
  } else {
    charIndex--;

    if (charIndex < 0) {
      deleting = false;
      charIndex = 0;
      wordIndex = (wordIndex + 1) % words.length;
    }
  }

  setTimeout(type, deleting ? 45 : 90);
}

type();

// Mobile menu
document.getElementById("menu").addEventListener("click", () => {
  document.getElementById("navLinks").classList.toggle("active");
});

document.querySelectorAll(".nav-links a").forEach(link => {
  link.addEventListener("click", () => {
    document.getElementById("navLinks").classList.remove("active");
  });
});

// 3D card tilt
document.querySelectorAll(".project, .skill").forEach(card => {
  card.addEventListener("pointermove", (e) => {
    if (e.pointerType === "touch") return;

    const rect = card.getBoundingClientRect();
    const x = (e.clientX - rect.left) / rect.width - 0.5;
    const y = (e.clientY - rect.top) / rect.height - 0.5;

    card.style.transform =
      `perspective(800px) rotateY(${x * 12}deg) rotateX(${-y * 12}deg) translateY(-5px)`;
  });

  card.addEventListener("pointerleave", () => {
    card.style.transform = "";
  });
});
</script>

</body>
</html>
