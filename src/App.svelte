<script>
  import Gradients from "./lib/Gradients.svelte";
  import Portfolio from "./lib/Portfolio.svelte";
  import Map from "./lib/Map.svelte";
  import Content from "./lib/Content.svelte";
  import SEO from "./lib/SEO.svelte";
  const views = [Gradients, Map]

  let currentView = 0
  let viewportComponent;

  $: viewportComponent = views[currentView]


</script>
<svelte:component this={viewportComponent}></svelte:component>
<div class="md:absolute m-auto w-full h-full top-10 content-center align-middle flex flex-col items-center justify-center z-50">
    <Content viewLength="{views.length}" bind:currentView="{currentView}"/>
    <Portfolio/>
</div>
<SEO/>
