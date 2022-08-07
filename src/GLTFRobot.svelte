<script>
	import * as SC from "svelte-cubed";
	import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
	import { onMount } from "svelte";

	const modelURL = "https://raw.githubusercontent.com/mrdoob/three.js/dev/examples/models/gltf/RobotExpressive/RobotExpressive.glb";
	let robot = null;
	
	function loadModel() {
		const loader = new GLTFLoader();
		return loader.loadAsync(modelURL)
	}

	onMount(() => {
		loadModel().then(model => robot = model);
	})
	
</script>

	{#if robot}
		 <SC.Primitive
			object={robot.scene}
			position={[0,0,0]}
			rotation={[0,0,0]}
			scale={[1,1,1]}
		>
		</SC.Primitive>
	{/if}
