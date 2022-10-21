<script>
  import Gradients from "./lib/Gradients.svelte";
  import Portfolio from "./lib/Portfolio.svelte";
  import Map from "./lib/Map.svelte";
  import Content from "./lib/Content.svelte";
  const views = [Gradients, Map]

  let currentView = 0
  let viewportComponent;

  $: viewportComponent = views[currentView]


</script>

<div class="absolute m-auto w-full h-full content-center align-middle flex flex-col items-center justify-center z-50">
    <Content viewLength="{views.length}" bind:currentView="{currentView}"/>
    <Portfolio/>
</div>
<svelte:component this={viewportComponent}></svelte:component>
