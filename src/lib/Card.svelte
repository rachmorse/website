<script>
  export let title;
  export let desc;
  export let link;
  export let image;
  export let alt;
  export let fit = "object-cover";
</script>

<div class="card carousel-item card-compact md:card-side bg-base-100 shadow-2xl mx-2 h-96 w-64 md:w-96 md:h-64">
  {#if image}
    <figure><img src="{image}" alt="{alt}" class="{fit} md:w-36 md:h-64 h-48 w-64"/></figure>
  {:else}
    <figure><img src="https://placeimg.com/200/280/arch" class="" alt="Movie"/></figure>
  {/if}
  <div class="card-body md:w-36">
    <h2 class="card-title">{title}</h2>
    <p>{desc}</p>
    {#if link}
      <div class="card-actions justify-end">
        <a class="btn btn-primary" href="{link}" target="_blank">Link</a>
      </div>
    {/if}
  </div>
</div>