<script>

    export let title;
    export let content;
    export let active_tag;
    let active_grid = -1;

    import Project from "./Project.svelte";
  
    
    import { cubicInOut } from 'svelte/easing';
	import { slide} from 'svelte/transition';

    let options = {duration: 150, easing: cubicInOut};

  </script>
  
  <div class="mb-5">
      <h2 class="text-3xl text-center">{title}</h2>

      <div class="grid gap-4 p-4 sm:grid-cols-2 ">
          {#each content as {title, desc, link, tags}, index}
              <Project link="{link}" desc="{desc}" title="{title}" tags="{tags}" active_tag="{active_tag}" bind:active_grid="{active_grid}" index="{index}"></Project>
              {#if active_grid == index}
              <div class=" mt-3 sm:hidden rounded-md bg-primary-200 p-3 w-full w-md mx-auto max-w-md" transition:slide={{...options, x: -150}}>
                <article class="prose m-auto" >
                    <h1>{content[active_grid].title}</h1>
                    <p>{content[active_grid].long_desc}</p>
                </article>
            </div>
            {/if}

              {#if index % 2 == 1 || index == content.length - 1}
                {#if active_grid == index || (active_grid % 2 == 0 && active_grid == index - 1)}
                  <div class=" mt-3 hidden sm:inline row-start-{Math.floor(index / 2) +2} rounded-md bg-primary-200 p-3 w-full sm:col-span-2" transition:slide={{...options, x: -150}}>
                      <article class="prose m-auto">
                          <h1>{content[active_grid].title}</h1>
                          <p>{content[active_grid].long_desc}</p>
                      </article>
                  </div>
                  {/if}
              {/if}
          {/each}


      </div>
  </div>