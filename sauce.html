
<html>

    <head>
        <title>domuko 2</title>
        <script type="text/javascript" src="three.js"></script>
        <script type="text/javascript" src="jquery-1.9.0.js"></script>
        <script type="text/javascript" src="TrackballControls.js"></script>
        <script type="text/javascript" src="stats.js"></script>
        <script type="text/javascript" src="dat.gui.js"></script>
        <style>
            body{
                /* set margin to 0 and overflow to hidden, to go fullscreen */
                margin: 0;
                overflow: hidden;
            }
        </style>
    </head>
    <body>
    
    <!-- Div which will hold the Output -->
    <div id="WebGL-output">
    </div>
    
    <!-- Javascript code that runs our Three.js examples -->
    <script type="text/javascript">
    
        // once everything is loaded, we run our Three.js stuff.
        $(function () {
    
            // create a scene, that will hold all our elements such as objects, cameras and lights.
            var scene = new THREE.Scene();
    
            // create a camera, which defines where we're looking at.
            var camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight, 0.1, 1000);
    
            // create a render and set the size
            var renderer = new THREE.WebGLRenderer();
    
            renderer.setClearColor(0xEEEEEE, 1.0);
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.shadowMapEnabled = true;
    
            // grindu lektuvas
            var planeGeometry = new THREE.PlaneGeometry(80, 120);
            var planeMaterial =  new THREE.MeshLambertMaterial({color: 0x013220});
            var planeMaterial2 =  new THREE.MeshLambertMaterial({opacity: 0.25, 
                transparent: true, 
                side: THREE.DoubleSide, 
                depthWrite: false});
            var plane = new THREE.Mesh(planeGeometry,planeMaterial);
            plane.receiveShadow  = true;
    
            plane.rotation.x = -0.5 * Math.PI;
            plane.position.x = 0;
            plane.position.y = 0;
            plane.position.z = 0;
            
            scene.add(plane);

            // position and point the camera to the center of the scene
            camera.position.x = -30;
            camera.position.y = 50;
            camera.position.z = 40;
            camera.lookAt(scene.position);
    
            // add ambientLight and spotlight for the shadows
            var ambiColor = "#0c0c0c";
            var ambientLight = new THREE.AmbientLight(ambiColor);
            scene.add(ambientLight);

            var spotLight = new THREE.SpotLight(0xffffff);
            spotLight.position.set(-40, 60, -10);
            spotLight.castShadow = true;
            scene.add(spotLight);
            
            var stairs;

            var handrailMesh;
            var handrail;
            var tubeMesh;
            var tube;
            var plane2;

            var extrude = {
                amount: 0,
                bevelThickness: 0.5,
                bevelSize: 0.5,
            };

            $("#WebGL-output").append(renderer.domElement);


            //........................................................................
            //menu





            var menu = new function () {

                this.steps = 15;
                this.rotationAngle = 10;
                this.offset = 10;
                this.ambientColor = "#0c0c0c";

                this.asGeom = function () {
                    // remove the old stairs
                    if(stairs != null){
                        scene.remove(stairs);
                        scene.remove(tubeMesh);
                        scene.remove(handrailMesh);
                        scene.remove(plane2)
                    }





                    // 2nd floor
                    plane2 = new THREE.Mesh(planeGeometry,planeMaterial2);
                    plane2.receiveShadow  = true;
                    plane2.rotation.x = -0.5 * Math.PI;
                    plane2.position.y = (0.5 + menu.steps) * 2;
                    plane2.position.x = 0;
                    plane2.position.z = 0;
                    scene.add(plane2);
                    //stairs
                    stairs = new THREE.Object3D();
                    for(i = 0; i < menu.steps; i++){
                        if(i % 2 == 0){
                            var stair = createMesh(new THREE.ExtrudeGeometry(LeftStair(), extrude));
                            stair.castShadow = true;
                            stairsRotation(stair, i);
                            changeStairoffset(stair, i);
                            rotateStair(stair);
                            stairs.add(stair);
                            var handrailThing = generateTube(handlePoints(), 0.25);
                            handrailThingMesh = createHandrailMesh(handrailThing);
                            handrailThingMesh.castShadow = true;
                            stairsRotation(handrailThingMesh, i);
                            changeStairoffset(handrailThingMesh, i);
                            stairs.add(handrailThingMesh);
                        } else {
                            var stair = createMesh(new THREE.ExtrudeGeometry(RighStair(), extrude));
                            stairsRotation(stair, i);
                            changeStairoffset(stair, i);
                            rotateStair(stair);
                            stair.castShadow = true;
                            stairs.add(stair);
                        }
                    }
                    scene.add(stairs);
                    // poles
                    tube = generateTube(handlePointsGen(5), 0.5);
                    tubeMesh = createHandrailMesh(tube);
                    tubeMesh.position.x = 20;
                    tubeMesh.castShadow = true;
                    scene.add(tubeMesh);
                    handrail = generateTube(handlePointsGen(10), 0.35);
                    handrailMesh = createHandrailMesh(handrail);
                    handrailMesh.position.x = 20;
                    handrailMesh.position.y = 10;
                    handrailMesh.position.z = 0;
                    handrailMesh.castShadow = true;
                    stairs.add(handrailMesh);
                };
            }

            //done



            var gui = new dat.GUI();
            gui.add(menu, 'steps', 0, 30).onChange(menu.asGeom);
            gui.add(menu, 'rotationAngle', 10, 45).onChange(menu.asGeom);
            gui.add(menu, 'offset', 0, 10).onChange(menu.asGeom);
            gui.addColor(menu, 'ambientColor').onChange(function (e) {
                ambientLight.color = new THREE.Color(e);
            });
            menu.asGeom();

            var controls = new THREE.TrackballControls(camera, renderer.domElement);
            render();
            function render() {
                controls.update();
                renderer.render(scene, camera);
                requestAnimationFrame(render);
            }


            //.................................................................

            function handlePoints(){
                var points = [];
                points.push(new THREE.Vector3(10, 1/2, 0));
                points.push(new THREE.Vector3(10, 10, 0));
                return points;
            }
            function handlePointsGen(rad){
                var points = [];
                for(var i = 0; i < menu.steps; i++){
                    points.push(new THREE.Vector3( -Math.cos((menu.rotationAngle * Math.PI / 180) * i) * (rad + menu.offset) ,
                                                    (0.5 + i) * 2,
                                                    -Math.sin((menu.rotationAngle * Math.PI / 180) * i) * (rad + menu.offset)));
                }
                return points;
            }

            function changeStairoffset (stair, i){
                stair.position.x = -Math.cos((menu.rotationAngle * Math.PI / 180) * i) * menu.offset;
                stair.position.z = -Math.sin((menu.rotationAngle * Math.PI / 180) * i) * menu.offset;
            }
            function stairsRotation(stair, i){
                stair.position.y = (0.5 + i) * 2;
                var axis = new THREE.Vector3(0, 1, 0);
                stair.rotateOnAxis(axis.normalize(), -menu.rotationAngle * i * Math.PI / 180);
            }
            function rotateStair(stair){
                var axisX = new THREE.Vector3(1, 0, 0);
                stair.rotateOnAxis(axisX.normalize(), Math.PI/2);
            }

            function RighStair(){
                var step = new THREE.Shape();
                step.moveTo(10, 0);
                step.lineTo(10, 2);
                step.quadraticCurveTo(20, 5, 20, 2);
                step.lineTo(20, 0);
                step.lineTo(10, 0);
                return step;
            }

            //VEIKIA

            function LeftStair(){
                var step = new THREE.Shape();
                step.moveTo(10, 0);
                step.lineTo(20, 0);
                step.lineTo(20, 2);
                step.quadraticCurveTo(10, 5, 10, 2);
                step.lineTo(10, 0);
                return step;
            }

            function generateTube(points, offset){
                var segments = 100;
                var offsetSegments = 0;
                var closed = false;
                var tubeGeometry = new THREE.TubeGeometry(new THREE.SplineCurve3(points), segments, offset, offsetSegments, closed);
                return tubeGeometry;
            }

            function createMesh(shape){
                shape.applyMatrix(new THREE.Matrix4().makeTranslation(-20, 0, 0));
                var meshMaterial = new THREE.MeshLambertMaterial({color: 0xb39577});
                var mesh = new THREE.Mesh(shape, meshMaterial)
                return mesh;
            }

            function createHandrailMesh(geom) {
                geom.applyMatrix(new THREE.Matrix4().makeTranslation(-20, 0, 0));
                var meshMaterial = new THREE.MeshPhongMaterial({color: 0xb3a7a7});
                var mesh = new THREE.Mesh(geom, meshMaterial)
                return mesh;
            }
        });
    </script>
    </body>
    </html>
    
