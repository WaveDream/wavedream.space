<!-- Logic -->
<script>
    // @ts-nocheck

    // import Nodes from "./components/Nodes.svelte";
    
        //Booleans
        let button_Bool = false;
        //Variables
        let _dec6_ = 5;
        let _dec8_ = 8;
        // let buffer = -200;
        //Keys (Static Arrays)
        const color_key = ["red", "orange", "yellow", "lime", "cyan", "blueviolet"]
        //Dynamic Arrays
        let orbColor = ["blueviolet", "red", "orange", "yellow", "lime", "cyan", "blueviolet", "red"]
        let zIndex = [7,6,5,4,3,2,1,0]
        let orbOpacity = [0,1,1,1,1,1,1,0]
        let orbSize = [0,10,20,30,40,50,60,70]
        //Functions
        function OrbStepper() {
            //Decrement Step Counters
            _dec6_--;
            _dec8_--;
            //Loop Step Counters
            if (_dec6_ < 0) {
                _dec6_ = 5;
            }
            if (_dec8_ < 0) {
                _dec8_ = 7;
            }
            //Opacity
            if (_dec8_ === 0) {
                orbOpacity.splice(7, 1, 0);
                orbOpacity.splice((_dec8_ + 1), 1, 1);
            } else if (_dec8_ === 7) {
                orbOpacity.splice((_dec8_ - 1), 1, 0);
                orbOpacity.splice(0, 1, 1);
            } else {
                orbOpacity.splice((_dec8_ - 1), 1, 0);
                orbOpacity.splice((_dec8_ + 1), 1, 1);
            }
            orbOpacity = orbOpacity;
            //Recolor
            orbColor.splice(_dec8_, 1, color_key[_dec6_]);
            orbColor = orbColor;
            //Resize
            orbSize.push(orbSize.shift());
            orbSize = orbSize;
            //Reorder (Z)
            zIndex.push(zIndex.shift());
            zIndex = zIndex;
        }
    </script>
<!-- Markup -->

<div id="orb-container"> 
    {#each zIndex as zIndex, i}
        <div 
            class={"orb " + i}
            style=
                "border: 1px solid {orbColor[i]};
                width: {orbSize[i] + "vh"};
                height: {orbSize[i] + "vh"};
                opacity: {orbOpacity[i]};
                z-index: {zIndex};">
        </div>
    {/each}

</div>


<!-- Styling  -->
<style>
    #orb-container {
        width: 100%;
        height: 100%;
        background: radial-gradient(circle at center, rgb(7, 0, 21), hsl(254, 89%, 10%) 20%, black 100%);
        position: relative;
        display: flex;
        top: 0;
        left: 0;
        justify-content: center;
        align-items: center;
    }

    .orb {
        border-radius: 50%;
        position: absolute;
        transition-property: width, height, opacity;
        transition-duration: .2s;
    }

    .orb:hover {
        border-width: 2px !important;
    }

</style>
