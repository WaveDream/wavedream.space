<script>
    import { Pane, Slider } from 'svelte-tweakpane-ui';

    let { value = $bindable(), ...props } = $props();
</script>

<div id="pane">
    <Pane title="Default Cube" position='inline'>        
        <Slider bind:value={value} wide={true} min={0} max={Math.PI * 2} label="Rotation" />
    </Pane>
</div>

<style>
    #pane {
        flex-basis: 80%;
    }
</style>