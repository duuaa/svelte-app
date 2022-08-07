<!-- <script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  import ReusableGLTF from "./ReusableGLTF.svelte";
  import { modelURL, updateModelStatus } from "./stores";

  function handleStatusChange(evt) {
    updateModelStatus(evt.detail.name, evt.detail.status);
  }
  let color = "black"
  let coloritem = new THREE.Color();
  let width = 1;
  let height = 1;
  let depth = 1;
  let spin = 0;
  function hey() {
    color="red"

    console.log(color);
    return false;
  }
</script>

<SC.Canvas   background={color} antialias>
  <SC.PerspectiveCamera
    position={[-10, 36, 20]}
    near={0.1}
    far={500}
    fov={40}
  />

  <SC.OrbitControls
    enabled={true}
    enableZoom={true}
    autoRotate={false}
    autoRotateSpeed={2}
    enableDamping={true}
    dampingFactor={0.1}
    target={[-6, 17, 0]}
  />

  <SC.DirectionalLight
    color={new THREE.Color(0xffffff)}
    position={[0, 10, 10]}
    intensity={0.75}
    shadow={false}
  />
  <SC.AmbientLight color={new THREE.Color(0xffffff)} intensity={0.75} />

  <ReusableGLTF
    modelURL={modelURL["littleCity"]}
    name="littleCity"
    scale={[0.05, 0.05, 0.05]}
    on:statusChange={handleStatusChange}
  />
</SC.Canvas>
<div>
  <span style="width:50%;">
    <label class="child" for="color"> change background color</label>
    <input class="child" on:change={hey} name="color" type="color" />
  </span>
</div>

<!-- <div class="controls">
  <label
    ><input type="range" bind:value={width} min={0.1} max={3} step={0.1} /> width</label
  >
  <label
    ><input type="range" bind:value={height} min={0.1} max={3} step={0.1} /> height</label
  >
  <label
    ><input type="range" bind:value={depth} min={0.1} max={3} step={0.1} /> depth</label
  >
</div>

<style>
  .controls {
    position: absolute;
  }
</style> -->

<!-- <style>
  /* Add a black background color to the top navigation */
  div {
    color: aliceblue;
    background-color: rgba(0, 0, 0, 0.971);
    position: fixed;
    width: 100%;
    margin: 0;
    padding: 1%;
    height: 10%;
  }
  .child {
    background-color: aliceblue;
    color: brown;
    display: inline-block;
    border: 1px solid red;
    border-radius: 20px;
    padding: 1rem 1rem;
    vertical-align: middle;
  }
</style>  -->

<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  import GLTFRobot from "./GLTFRobot.svelte";
  let color = "#0195BB"
  </script>
  
  <SC.Canvas
    background={new THREE.Color(color)}
    antialias
  >
  
    <SC.PerspectiveCamera 
      position={[0,5,10]}
      near={0.1}
      far={400}
      fov={60}
    />
  
    <SC.OrbitControls 
      enabled={true}
      enableZoom={true}
      autoRotate={true}
      autoRotateSpeed={2}
      enableDamping={true}
      dampingFactor={0.1}
    />
  
    <SC.DirectionalLight
      color={new THREE.Color("#ffffff")}
      position={[0,10,10]}
  
    />
    <SC.AmbientLight
      color={new THREE.Color("#ffffff")}
      intensity={0.85}
    />
    
    <GLTFRobot />
  </SC.Canvas>
  <div class="controls">
    <span style="width:50%;">
      <label class="child" for="color"> change background color</label>
      <input class="child"  name="color" type="color" bind:value={color}/>
    </span>
  </div>
  <style>
    /* Add a black background color to the top navigation */
    div {
      color: aliceblue;
      background-color: rgba(0, 0, 0, 0.971);
      position: fixed;
      width: 100%;
      margin: 0;
      padding: 1%;
      height: 10%;
    }
    .child {
      background-color: aliceblue;
      color: brown;
      display: inline-block;
      border: 1px solid red;
      border-radius: 20px;
      padding: 1rem 1rem;
      vertical-align: middle;
    }
  </style>