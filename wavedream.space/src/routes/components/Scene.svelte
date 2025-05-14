<script>
  import { T } from '@threlte/core'

  let { r } = $props();
</script>

<T.PerspectiveCamera
  makeDefault
  position={[10, 10, 10]}
  oncreate={(ref) => {
    ref.lookAt(0, 0, 0)
  }}
/>

<T.DirectionalLight 
  position={[10, 20, 10]}
  intensity={2}
  castShadow
/>

<T.Mesh   rotation.y={r} rotation.z={r * .5}>
  <T.BoxGeometry args={[5, 5, 5]} />
  <T.MeshStandardMaterial color="grey" />
</T.Mesh>
