
<script>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";


let time = 0;

let increase = document.querySelector(".increase");
let decrease = document.querySelector(".decrease");

increase.addEventListener("click", () => {
  time += 0.0002;
})
decrease.addEventListener("click", () => {
  time -= 0.0002;
})

//-----------------------------------------------------SKY BOX



const textureLoaderSkybox = new THREE.TextureLoader();
const texture = textureLoaderSkybox.load('/src/assets/img/sphere.webp');

// Création du matériau de la skybox
const material = new THREE.MeshBasicMaterial({ map: texture, side: THREE.DoubleSide });

// Création de la géométrie de la skybox
const geometry = new THREE.SphereGeometry(4000, 4000, 4000);

// Création de la skybox
const skybox = new THREE.Mesh(geometry, material);

// Ajout de la skybox à la scène



const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(50, window.innerWidth / window.innerHeight, 0.1, 10000);

const renderer = new THREE.WebGLRenderer({

  antialias: true
});
// scene.background = new THREE.Color(0x002035);
renderer.setSize(window.innerWidth, window.innerHeight);

const controls = new OrbitControls(camera, renderer.domElement);
camera.position.set(0, 20, 100);
controls.update();

renderer.setPixelRatio(2);
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);



var textureLoader = new THREE.TextureLoader();
var neptuneTexture = textureLoader.load('/src/assets/img/neptune.webp');

var textureLoader = new THREE.TextureLoader();
var uranusTexture = textureLoader.load('/src/assets/img/uranus.webp');

var textureLoader = new THREE.TextureLoader();
var saturnTexture = textureLoader.load('/src/assets/img/saturn.webp');

var textureLoader = new THREE.TextureLoader();
var ringsTexture = textureLoader.load('/src/assets/img/rings.webp');

var textureLoader = new THREE.TextureLoader();
var sunTexture = textureLoader.load('/src/assets/img/sun.webp');

var textureLoader = new THREE.TextureLoader();
var jupiterTexture = textureLoader.load('/src/assets/img/jupiter.webp');

var textureLoader = new THREE.TextureLoader();
var marsTexture = textureLoader.load('/src/assets/img/mars.webp');

var textureLoader = new THREE.TextureLoader();
var earthTexture = textureLoader.load('/src/assets/img/earth.webp');

var textureLoader = new THREE.TextureLoader();
var cloudTexture = textureLoader.load('/src/assets/img/clouds.webp');

var textureLoader = new THREE.TextureLoader();
var venusTexture = textureLoader.load('/src/assets/img/venus.webp');

var textureLoader = new THREE.TextureLoader();
var mercuryTexture = textureLoader.load('/src/assets/img/mercury.webp');



// var fondLoader = new THREE.TextureLoader();
// var fond = fondLoader.load('fond.jpg');
// scene.background = fond;

// renderer.setClearColor(0, 1, 43);



var neptuneGeometry = new THREE.SphereGeometry(0.466, 50, 30);
var neptuneMaterial = new THREE.MeshStandardMaterial({ map: neptuneTexture });
var neptune = new THREE.Mesh(neptuneGeometry, neptuneMaterial);
const neptuneAngularSpeed = 0.0012;
const neptuneRadius = 90;
let neptuneAngle = 0;

var uranusGeometry = new THREE.SphereGeometry(0.494, 50, 30);
var uranusMaterial = new THREE.MeshStandardMaterial({ map: uranusTexture });
var uranus = new THREE.Mesh(uranusGeometry, uranusMaterial);
const uranusAngularSpeed = 0.0016;
const uranusRadius = 80;
let uranusAngle = 0;

var saturnGeometry = new THREE.SphereGeometry(1.685, 50, 40);
var saturnMaterial = new THREE.MeshPhongMaterial({ map: saturnTexture });
var saturn = new THREE.Mesh(saturnGeometry, saturnMaterial);
const saturnAngularSpeed = 0.0018;
const saturnRadius = 70;
let saturnAngle = 0;

var ringsGeometry = new THREE.RingGeometry(1.8, 4.0, 40);
var ringsMaterial = new THREE.MeshPhongMaterial({ map: ringsTexture, side: THREE.DoubleSide, alphaTest: 0.5 });
var rings = new THREE.Mesh(ringsGeometry, ringsMaterial);
const ringsAngularSpeed = 0.0018;
const ringsRadius = 70;
let ringsAngle = 0;

var jupiterGeometry = new THREE.SphereGeometry(2.0, 50, 40);
var jupiterMaterial = new THREE.MeshPhongMaterial({ map: jupiterTexture });
var jupiter = new THREE.Mesh(jupiterGeometry, jupiterMaterial);
const jupiterAngularSpeed = 0.002;
const jupiterRadius = 60;
let jupiterAngle = 0;


var marsGeometry = new THREE.SphereGeometry(0.078, 50, 30);
var marsMaterial = new THREE.MeshLambertMaterial({ map: marsTexture });
var mars = new THREE.Mesh(marsGeometry, marsMaterial);
const marsAngularSpeed = 0.0023;
const marsRadius = 50;
let marsAngle = 0;

var earthGeometry = new THREE.SphereGeometry(0.1098, 50, 30);
var earthMaterial = new THREE.MeshLambertMaterial({ map: earthTexture, alphaMap: cloudTexture });
var earth = new THREE.Mesh(earthGeometry, earthMaterial);
const earthAngularSpeed = 0.0024;
const earthRadius = 40;
let earthAngle = 0;

var venusGeometry = new THREE.SphereGeometry(0.104, 50, 30);
var venusMaterial = new THREE.MeshLambertMaterial({ map: venusTexture });
var venus = new THREE.Mesh(venusGeometry, venusMaterial);
const venusAngularSpeed = 0.0025;
const venusRadius = 30;
let venusAngle = 0;

var orbitVenusGeometry = new THREE.RingGeometry(269.5, 270.5, 50);
var orbitVenusMaterial = new THREE.MeshBasicMaterial({ color: 0xffffff, side: THREE.DoubleSide });
var orbitVenus = new THREE.Mesh(orbitVenusGeometry, orbitVenusMaterial);

var mercuryGeometry = new THREE.SphereGeometry(0.041, 50, 30);
var mercuryMaterial = new THREE.MeshLambertMaterial({ map: mercuryTexture });
var mercury = new THREE.Mesh(mercuryGeometry, mercuryMaterial);
const mercuryAngularSpeed = 0.0026;
const mercuryRadius = 20;
let mercuryAngle = 0;

var orbitMercuryGeometry = new THREE.RingGeometry(259.5, 260.5, 50);
var orbitMercuryMaterial = new THREE.MeshBasicMaterial({ color: 0xffffff, side: THREE.DoubleSide });
var orbitMercury = new THREE.Mesh(orbitMercuryGeometry, orbitMercuryMaterial);



var sunGeometry = new THREE.SphereGeometry(19.6, 100, 50);
var sunMaterial = new THREE.MeshBasicMaterial({ map: sunTexture, reflectivity: 2 });
var sun = new THREE.Mesh(sunGeometry, sunMaterial);


sun.add(neptune);
sun.add(uranus);
sun.add(rings);
sun.add(saturn);
sun.add(jupiter);
sun.add(mars);
sun.add(earth);
sun.add(venus);
// sun.add(orbitVenus);
sun.add(mercury);
// sun.add(orbitMercury);
scene.add(sun);
scene.add(skybox);


sun.position.x = 0;
rings.rotation.x = 30;
rings.rotation.y = 0.2;
// orbitVenus.rotation.x = 1.5708;
// orbitMercury.rotation.x = 1.5708;

// const axesHelper = new THREE.AxesHelper(600);
// scene.add(axesHelper);

camera.position.y = 500;


var light = new THREE.PointLight(0xffffff, 1);
light.position.set(0, 0, 0);
scene.add(light);




function animate() {

  requestAnimationFrame(animate)
  controls.update();


  neptuneAngle += (neptuneAngularSpeed + time);
  var x = neptuneRadius * Math.sin(neptuneAngle);
  var y = 0;
  var z = neptuneRadius * Math.cos(neptuneAngle);
  neptune.position.set(x, y, z);

  uranusAngle += (uranusAngularSpeed + time);
  var x = uranusRadius * Math.sin(uranusAngle);
  var y = 0;
  var z = uranusRadius * Math.cos(uranusAngle);
  uranus.position.set(x, y, z);

  saturnAngle += (saturnAngularSpeed + time);
  var x = saturnRadius * Math.sin(saturnAngle);
  var y = 0;
  var z = saturnRadius * Math.cos(saturnAngle);
  saturn.position.set(x, y, z);

  ringsAngle += (ringsAngularSpeed + time);
  var x = ringsRadius * Math.sin(ringsAngle);
  var y = 0;
  var z = ringsRadius * Math.cos(ringsAngle);
  rings.position.set(x, y, z);

  jupiterAngle += (jupiterAngularSpeed + time);
  var x = jupiterRadius * Math.sin(jupiterAngle);
  var y = 0;
  var z = jupiterRadius * Math.cos(jupiterAngle);
  jupiter.position.set(x, y, z);

  marsAngle += (marsAngularSpeed + time);
  var x = marsRadius * Math.sin(marsAngle);
  var y = 0;
  var z = marsRadius * Math.cos(marsAngle);
  mars.position.set(x, y, z);

  earthAngle += (earthAngularSpeed + time);
  var x = earthRadius * Math.sin(earthAngle);
  var y = 0;
  var z = earthRadius * Math.cos(earthAngle);
  earth.position.set(x, y, z);

  venusAngle += (venusAngularSpeed + time);
  var x = venusRadius * Math.sin(venusAngle);
  var y = 0;
  var z = venusRadius * Math.cos(venusAngle);
  venus.position.set(x, y, z);

  mercuryAngle += (mercuryAngularSpeed + time);
  var x = mercuryRadius * Math.sin(mercuryAngle);
  var y = 0;
  var z = mercuryRadius * Math.cos(mercuryAngle);
  mercury.position.set(x, y, z);



  rings.rotation.z += 0.0005;
  sun.rotation.y += 0.0001;
  jupiter.rotation.y += 0.005
  renderer.render(scene, camera);
};

animate();





var raycaster = new THREE.Raycaster();

// Fonction pour gérer les événements de clic
function onMouseClick(event) {
  // Récupérer la position de la souris dans les coordonnées de la scène
  var mouse = new THREE.Vector2();
  mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
  mouse.y = - (event.clientY / window.innerHeight) * 2 + 1;

  // Mettre à jour le raycaster avec la position de la souris
  raycaster.setFromCamera(mouse, camera);

  // Détecter les intersections entre le rayon et les objets de la scène
  var intersects = raycaster.intersectObjects(scene.children);

  // Si un objet est intersecté, traiter l'événement de clic
  if (intersects.length > 0) {
    var object = intersects[0].object;

    // Vérifier si l'objet intersecté est l'anneau
    if (object === sun) {
      console.log("Soleil")
    }
    if (object === mercury) {
      console.log("Mercure")
    }
    if (object === venus) {
      console.log("Venus")
    }
    if (object === earth) {
      console.log("La terre")
    }
    if (object === mars) {
      console.log("Mars")
    }
    if (object === jupiter) {
      console.log("jupiter")
    }
    if (object === saturn) {
      console.log("Saturne")
    }
    if (object === uranus) {
      console.log("Uranus")
    }
    if (object === neptune) {
      console.log("Neptune")
    }
  }
}
document.addEventListener('click', onMouseClick);
</script>

<template>


</template>

<style scoped>

</style>
