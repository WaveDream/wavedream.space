<script>
    import "../app.css";
    import Orbs from "./components/Orbs.svelte";
    // import { Pane, Slider } from 'svelte-tweakpane-ui';
	import Output from "./components/Output.svelte";
    import XyPad from "./components/XyPad.svelte";
            
    let r = $state(0.5);
    let z = $state(0.5);
    let s = $state(0.5);



</script>

<div id='main'>

    <div id='orbs'>
        <Orbs />
    </div>

    <div id="sidebar">
        <div>
            <div id='output'>
                    <Output r={r} z={z} s={s} />
            </div>
        </div>
        <div class="flex flex-col basis-full">
            <div id="module" class="flex basis-1/16 justify-center items-center bg-gray-800 h-10">
                <div><h2 class="text-gray-400">SphereHelix</h2></div>
            </div>
            <div class="basis-7/16"></div>
            <div id="controls" class="basis-8/16 w-full">
                <XyPad bind:rotate={r} bind:zoom={z} />

            </div>    
        </div>
    </div>
</div>

<style>

    #main {
        background-color: orange;
        display: flex;
        width: 100vw;
        height: 100vh;
    }

    #orbs {
        z-index: 1;
        flex-basis: 70%;
    }

    #sidebar {
        display: flex;
        flex-direction: column;
        z-index: 2;
        flex-basis: 30%;
        background-color: rgb(28, 31, 43);
    }

    #output {
        width: 100%;
        aspect-ratio: 16 / 9;
        opacity: 100%;
        background-color: grey;
    }

</style>