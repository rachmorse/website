<script>
  import Gradients from "./lib/Gradients.svelte";
  import Portfolio from "./lib/Portfolio.svelte";
</script>

<div class="absolute m-auto w-full h-full content-center align-middle flex items-center justify-center">
    <div>
        <h1 class="align-middle">Hi, I'm Dan Hirst</h1>
        <h2>Developer, data scientist, map nerd</h2>
        <button class="btn-primary m-5">Click</button>
    </div>

</div>
<Portfolio/>
<Gradients/>

<style>
    div {
        font-family: 'Josefin Sans', sans-serif;
    }
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@700&family=Truculenta:opsz,wght@12..72,500&display=swap');
</style>