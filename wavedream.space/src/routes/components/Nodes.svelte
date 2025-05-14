<script>
  let i = 0;

</script>

<div id="nodeContainer">
  <div class="node"></div>
</div>

<style lang="postcss">
#nodeContainer {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}

  .node {
    background-color: red;
    border-radius: 50%;
    transform: translateY(-5vh);
    width: 15px;
    height: 15px;
    z-index: 20;

  }
  .node:hover {
    width: 20px;
    height: 20px;
  }
</style>