<script>
  export let title;
  export let desc;
  export let link;
  export let image;
  export let alt;
</script>

<div class="card carousel-item card-compact card-side bg-base-100 shadow-2xl mx-2 w-96 h-64">
  {#if image}
    <figure><img src="{image}" alt="{alt}" class="object-cover w-36 h-64"/></figure>
  {:else}
    <figure><img src="https://placeimg.com/200/280/arch" class="" alt="Movie"/></figure>
  {/if}
  <div class="card-body w-36">
    <h2 class="card-title">{title}</h2>
    <p>{desc}</p>
    {#if link}
      <div class="card-actions justify-end">
        <a class="btn btn-primary" href="{link}" target="_blank">Link</a>
      </div>
    {/if}
  </div>
</div>