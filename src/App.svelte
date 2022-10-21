<script>
  import Gradients from "./lib/Gradients.svelte";
  import Portfolio from "./lib/Portfolio.svelte";
  import { Github, Linkedin, Twitter} from "lucide-svelte";
</script>

<div class="absolute m-auto w-full h-full content-center align-middle flex flex-col items-center justify-center">
    <div>
        <div class="my-10">
           <h1 class="my-3 text-8xl">Hi, I'm Dan Hirst</h1>
            <h2 class="text-3xl">Developer, data scientist, map nerd</h2>
        </div>

        <div class="grid grid-cols-3 grid-rows-1 grid-flow-row gap-4 text-center m-5">
            <a href="https://github.com/dchirst" class="btn btn-circle m-auto"><Github/></a>
            <a href="https://www.linkedin.com/in/dan-hirst/" class="btn btn-circle m-auto"><Linkedin/></a>
            <a href="https://twitter.com/dchirst0" class="btn btn-circle m-auto"><Twitter/></a>
        </div>
        <button class="btn-primary m-5">Click</button>
    </div>
    <Portfolio/>

</div>
<Gradients/>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Josefin+Sans:wght@700&family=Truculenta:opsz,wght@12..72,500&display=swap');
    h1, h2 {
        font-family: 'Abril Fatface', cursive;
    }
</style>