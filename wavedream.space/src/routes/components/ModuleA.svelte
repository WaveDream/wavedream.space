<script>
    import Scene from "./Scene.svelte";
    import { Canvas } from "@threlte/core";

    let { r } = $props();
</script>

<div id="container">
    <div id="s1">
        <Canvas>
            <Scene r={r} />
        </Canvas>
    </div>
    <div id="s2">
        <Canvas>
            <Scene r={r} />
        </Canvas>
    </div>
</div>

<style>
    #container {
        width: 30%;
    }

    #s1 {
        position: absolute;
        width: inherit;
        aspect-ratio: 16 / 9;
        opacity: 100%;
        mix-blend-mode: difference;
    }

    #s2 {
        position: absolute;
        width: inherit;
        aspect-ratio: 16 / 9;
        top: 0;
        opacity: 100%;
        mix-blend-mode: normal;
    }
</style>