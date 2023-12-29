<script>

    export let title;
    export let content;

    import Project from "./Project.svelte";
  
  
      
      let tags = content 
          .map(x => x.tags)
          .flat();
      let unique_tags = [...new Set(tags)];

      let active_tag = "";
  
      function set_active_tag(event) {
        let tag_id = event.target.id;
        if (active_tag == tag_id) {
          active_tag = "";
        } else {
          active_tag = tag_id;
        }
      }
  
  
  </script>
  
  <div>
      <h2 class="text-3xl text-center">{title}</h2>
      {#each unique_tags as tag}
          <button on:click={set_active_tag} id="{tag}" class="inline-block m-1">{tag}</button>
      {/each}
      <div class="grid gap-4 p-4 sm:grid-cols-2">
          {#each content as {title, desc, link, tags}}
              <Project link="{link}" desc="{desc}" title="{title}" tags="{tags}" active_tag="{active_tag}"></Project>
          {/each}
      </div>
  </div>