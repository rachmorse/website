<script>
    import { Github, Linkedin, Twitter} from "lucide-svelte";

    // export let viewLength;
    // export let currentView;

    // function updateViewport() {
    //   let newView = Math.floor(Math.random() * viewLength);
    //   if (newView === currentView) {
    //       if (newView < viewLength - 1) {
    //           newView++;
    //       } else {
    //           newView--;
    //       }
    //   }
    //   currentView = newView;
//   }
</script>
<div class="z-50">
    <div class="md:my-10 mt-20 mb-10 ">
       <h1 class="my-3 text-white text-5xl md:text-8xl">Hi, I'm Dan Hirst</h1>
        <h2 class=" text-2xl md:text-3xl">Developer, data scientist, map nerd</h2>
    </div>

    <div class="grid grid-cols-3 grid-rows-1 grid-flow-row gap-4 text-center m-5">
        <a href="https://github.com/dchirst" class="btn btn-circle m-auto"><Github/></a>
        <a href="https://www.linkedin.com/in/dan-hirst/" class="btn btn-circle m-auto"><Linkedin/></a>
        <a href="https://twitter.com/dchirst0" class="btn btn-circle m-auto"><Twitter/></a>
    </div>
    <!-- <button class="btn-primary m-5" on:click={updateViewport}>Click</button> -->
</div>

<style>
</style>
