# lab9
part1 :
This is the returned json data for student information management system

    {
        "Username": "Hulk007633",
        "Student Name": "John Wick",
        "StudentNo": "ts0011223",
        "Sex": "male",
        "Phone": "111999922222",
        "Dormitory": "North 4",

        "Selected Courses": [
            {
                "Course Name": "Operating System",
                "CoursesNo": "CS20220101",
                "Course Score": "97" 
            },
            {
                "Course Name": "Computer Network",
                "CoursesNo": "CS20220102",
                "Course Score": "97" 
            },
            {
                "Course Name": "Data Structure",
                "CoursesNo": "CS20220103",
                "Course Score": "97" 
            }
        ]
    }

part2:

Open this url:
https://playground.babylonjs.com/#2KRNG9#4

Copy the code below:

var createScene = function () {
    // This creates a basic Babylon Scene object (non-mesh)
    var scene = new BABYLON.Scene(engine);

    var camera = new BABYLON.ArcRotateCamera("camera", BABYLON.Tools.ToRadians(90), BABYLON.Tools.ToRadians(65), 10, BABYLON.Vector3.Zero(), scene);

    // This attaches the camera to the canvas
    camera.attachControl(canvas, true);

    // This creates a light, aiming 0,1,0 - to the sky (non-mesh)
    var light = new BABYLON.HemisphericLight("light", new BABYLON.Vector3(0, 1, 0), scene);

    // Default intensity is 1. Let's dim the light a small amount
    light.intensity = 0.9;

    // Our built-in 'ground' shape.
    var ground = BABYLON.MeshBuilder.CreateGround("ground", {width: 10, height: 8}, scene);
    let groundMaterial = new BABYLON.StandardMaterial("A dog", scene);
    ground.material = groundMaterial;
    let groundTexture = new BABYLON.Texture("https://upload.wikimedia.org/wikipedia/commons/8/87/Alaskan_Malamute%2BBlank.png", scene);
    groundTexture.hasAlpha = true;
    ground.material.diffuseTexture = groundTexture;

    BABYLON.SceneLoader.ImportMesh("", Assets.meshes.Alien.rootUrl, Assets.meshes.Alien.filename, scene, function(newMeshes){
        newMeshes[0].scaling = new BABYLON.Vector3(5, 5, 5);
        newMeshes[0].position.y += 3.5;
    });

    return scene;
};
