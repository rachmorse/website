<script>

    export let title;
    export let content;
    export let active_tag;

    import Project from "./Project.svelte";
  
    
  
  </script>
  
  <div class="mb-5">
      <h2 class="text-3xl text-center">{title}</h2>

      <div class="grid gap-4 p-4 sm:grid-cols-2">
          {#each content as {title, desc, link, tags}}
              <Project link="{link}" desc="{desc}" title="{title}" tags="{tags}" active_tag="{active_tag}"></Project>
          {/each}
      </div>
  </div>