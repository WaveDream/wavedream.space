<script>
    import "../app.css";
    import Orbs from "./components/Orbs.svelte";
    // import { Pane, Slider } from 'svelte-tweakpane-ui';
	import Output from "./components/Output.svelte";
            
    let r = $state(0);



</script>

<div id='main'>
    <div id='orbs'>
        <Orbs />
    </div>
    <div id="modules">
        <div>
            <div id='output'>
                    <Output r={r} />
            </div>
        </div>
            <!-- <div id="slot">

                <DefaultCube bind:value={r} />

                <div id="l">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="var(--color-l)" stroke-linecap="round" stroke-linejoin="round" width="20" height="20" stroke-width="2"> <path d="M5 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M19 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M5 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M19 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M5 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> <path d="M19 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path> </svg> 
                </div>

                <div id="r">
                    <svg width="24" height="24" stroke-width="2" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" stroke="var(--color-r)"><path d="M6.75827 17.2426L12.0009 12M17.2435 6.75736L12.0009 12M12.0009 12L6.75827 6.75736M12.0009 12L17.2435 17.2426" stroke="#grey" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path></svg>
                </div>

            </div>      -->
        <div>

            
            <div id="sliders">

                <div class="flex align-items-center justify-content-center">
                    <div>
                        <span>Rotation</span>
                    </div>
                    <div>
                        <input type="range" min="0" max="1" step="0.001" bind:value={r} class="range range-sm range-primary" />
                    </div>
                </div>

                <div class="flex align-items-center justify-content-center">
                    <div>
                        <span>Zoom</span>
                    </div>
                    <div>
                        <input type="range" min="0" max="1" step="0.001" bind:value={r} class="range range-sm range-secondary" />
                    </div>
                </div>

                <div class="flex align-items-center justify-content-center">
                    <span>Scale</span>
                    <input type="range" min="0" max="1" step="0.001" bind:value={r} class="range range-sm range-accent" />
                </div>   
                
            </div>
            
        </div>
    </div>
</div>

<style>

    #sliders {
        margin: 10px;
    }

    span {
        margin: 20px;
    }

    /* #l {
        background-color: hsl(230, 7%, 17%);
        display: flex;
        align-items: center;
        justify-content: center;
        flex-basis: 10%;
        border-right: 1px dashed rgb(70, 70, 70);
        cursor: move;
        --color-l: grey;
    }

    #l:hover {
        --color-l: rgb(180, 180, 180);
    }

    #r {
        background-color: hsl(230, 7%, 17%);
        display: flex;
        align-items: center;
        justify-content: center;
        flex-basis: 10%;
        cursor: pointer;
        --color-r: grey;

    }

    #r:hover {
        background-color: rgb(201, 80, 80);
        --color-r: white;
    }

    #slot {
        display: flex;
    } */
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

    #modules {
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