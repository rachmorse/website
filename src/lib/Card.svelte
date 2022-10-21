<script>
  export let title;
  export let desc;
  export let link;
  export let image;
</script>

<div class="card carousel-item card-compact card-side bg-base-100 shadow-2xl mx-2 w-96 h-64">
  <figure><img src="https://placeimg.com/200/280/arch" alt="Movie"/></figure>
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