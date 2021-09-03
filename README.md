# three.js-collabrativesphere-plane

<!DOCTYPE html>
<html>
    <head>
        <title>THREE.JS</title>
    </head>
    <body>
    <div class="centre">THREE.JS</div>
    </head>
    <body>
    <div></div>
    <div></div>
    <div class="img">
        <img  src="https://www.linkpicture.com/q/Screenshot_20210903-143012_Snapchat-01.jpeg" width="400" height="400" class="rotate90">
    </div>
    <canvas></canvas>
    <meta charset=utf-8></meta>
    <style>
        .rotate90 {
  -webkit-transform:rotate(-90deg);
  -moz-transform: rotate(-90deg);
  -ms-transform: rotate(-90deg);
  -o-transform: rotate(-90deg);
  transform: rotate(-90deg);
  filter: saturate(2);
         }
        .img{
            text-align: center;
        }
        body{
            width:100%;
            height:100%;
            margin:0;
        }
        .centre{
            font-size: 50px;
            text-align: center;
        }
        canvas{
            width:100%;,height:100%;
        }
    </style>
        <script src= "https://threejs.org/build/three.js">
        </script>
        <script>
         function start(){
var scene =new THREE.Scene();
var camera =new THREE.PerspectiveCamera(60,1,0.1,1000);
var render =new THREE.WebGLRenderer();
render.setSize(window.innerWidth,window.innerHeight);
document.body.appendChild(render.domElement);
var sphere = new THREE.SphereGeometry(30,32,16)
var terrain =new THREE.BoxGeometry(100,100,16,16);
var circlem = new THREE.MeshBasicMaterial({color:"yellow",wireframe:true})
var circle =new THREE.Mesh(sphere,circlem)
circle.position.x = 90
circle.position.y = 30
scene.add(circle)
var material =new THREE.MeshBasicMaterial({color:"white",wireframe:true,
visible:true});
camera.position.z = 200
camera.position.x +=100
var plane = new THREE.Mesh(terrain,material);
scene.add(plane);
plane.position.x += 90
plane.position.z -= 10
plane.position.y -= 40
plane.rotation.x +=90
function anim(){
    render.render(scene,camera)
    circle.rotation.y += 0.01
    circle.rotation.x +=0.01
    plane.rotation.z +=0.01
    requestAnimationFrame(anim)
}
anim()

}
window.onload=function(){
    start()
}

        </script>
    </body>
</html>
