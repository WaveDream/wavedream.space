<script>
    import "../app.css";
    import Orbs from "./components/Orbs.svelte";
    // import { Pane, Slider } from 'svelte-tweakpane-ui';
	import Output from "./components/Output.svelte";
            
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
            <div class="basis-13/16"></div>
            <div id="controls" class="basis-2/16">
                <div id="sliders">
                    <div class="flex align-items-center justify-content-center">
                        <div class="basis-1/4">
                            <span>Rotate</span>
                        </div>
                        <div class="basis-3/4">
                            <input type="range" min="0" max="1" step="0.001" bind:value={r} class="range range-sm range-primary" />
                        </div>
                    </div>

                    <div class="flex align-items-center justify-content-center">
                        <div class="basis-1/4">
                            <span>Zoom</span>
                        </div>
                        <div class="basis-3/4">
                            <input type="range" min="0" max="1" step="0.001" bind:value={z} class="range range-sm range-secondary" />
                        </div>
                    </div>

                    <!-- <div class="flex align-items-center justify-content-center">
                        <div class="basis-1/4">
                            <span>Scale</span>
                        </div>
                        <div class="basis-3/4">
                            <input type="range" min="0" max="1" step="0.001" bind:value={s} class="range range-sm range-accent" />
                        </div>
                    </div>    -->
                    
                </div>
            </div>    
            </div>
    </div>
</div>

<style>

    #sliders {
        margin: 10px;
        width: 100%;
    }

    span {
        color: rgb(100, 122, 141);
        margin: 20px;
        -webkit-user-select: none; /* Safari */
        -ms-user-select: none; /* IE 10 and IE 11 */
        user-select: none; /* Standard syntax */
    }

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