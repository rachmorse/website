<script>
   import Carousel from "./Carousel.svelte";
    let current = "code";
</script>
<div class="flex flex-col space-y-5 w-screen">
  <div class="tabs tabs-boxed m-auto">
    <a class="tab tab-lg {current === 'code' ? 'tab-active': ''}" on:click={() => current = 'code'}>Code</a>
    <a class="tab tab-lg {current === 'blogs' ? 'tab-active': ''}" on:click={() => current = 'blogs'}>Blogs</a>
    <a class="tab tab-lg {current === 'other' ? 'tab-active': ''}" on:click={() => current = 'other'}>Other</a>
  </div>
  <Carousel {current}/>
</div>


<div></div>