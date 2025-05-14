<script lang="ts">
    import { T, useTask } from '@threlte/core'
    import { Instance, InstancedMesh, FakeGlowMaterial, Sky } from '@threlte/extras'
	import { AmbientLight } from 'three';
    let dn = $state(Date.now())
    useTask(() => (dn = Date.now()))

    let { r, z, s } = $props();
  </script>

<T.PerspectiveCamera
makeDefault
zoom={z}
position={[0, -1, 10]}
oncreate={(ref) => {
  ref.lookAt(0, 0, 0)

}}
/>

  <Sky elevation={-3} />

  <InstancedMesh 
    rotation.y={r * 2 * Math.PI}
    rotation.x={r * Math.PI}
    rotation.z={r * Math.PI}
  >
    <T.MeshPhysicalMaterial color="#049ef4" iridescence={1} ior={1.5} iridescenceIOR={1.8} metalness={1} />
    <T.SphereGeometry args={[.5]} />

    {#each { length: 50 }, i}
    <Instance
      position.x={(i/2) - 5}
      position.y={Math.sin((dn / 4000) * i) * 3}
      position.z={Math.cos((dn / 4000) * i) * 3}
      scale={s * 2}
    />
    {/each}

  </InstancedMesh>

  <T.DirectionalLight position={[0, -10, 10]} intensity={5} />



