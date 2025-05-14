<script>
    let { rotate = $bindable(), zoom = $bindable() } = $props();
</script>

<div id="container basis-full">
    <div class="flex flex-col basis-full justify-center">
        <div id="title" class="flex justify-center align-middle bg-gray-800">
            <h2>XY Pad</h2>
        </div>

        <div id="rotate" class= "flex flex-col justify-center items-center basis-20">
            <div>
                <span>Rotate</span>
            </div>
            <div class="">
                <input class="rotate" type="range" min="0" max="1" step="0.001" bind:value={rotate}>
            </div>
            
        </div>

        <div id="mid" class="flex justify-center align-middle">
            <div class="basis-1/4 flex flex-col justify-center items-center">
                
                <div class="">
                    <input type="range" class="inputvert" min="0" max="1" step="0.001" bind:value={zoom}>
                </div>

                <div class="basis-1/16">
                    <span class='zoom'>Zoom</span>
                </div>
            </div>

            <div class="xypad basis-1/2 bg-gray-900"></div>

            <div class="basis-1/4">

            </div>
        </div>

        <div class="basis-10">

        </div>

    </div>
</div>

<style>
    input {
        width: 180px;
    }

    .rotate {
        width: 180px;
        accent-color: rgb(80, 43, 226);
    }

    .inputvert {
        appearance: slider-vertical;
        -moz-appearance: slider-vertical;
        -webkit-appearance: slider-vertical;
        height: 180px;
        width: 20px;
        accent-color: rgb(80, 43, 226);
    }

    .xypad {
        width: 250px;
        height: 250px;
        aspect-ratio: 1;
        border-radius: 10%;
        border: 2px solid;
        border-color: rgb(80, 43, 226);
        
    }


</style>