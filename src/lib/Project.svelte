<script>
    export let link;
    export let title;
    export let desc;
    export let tags;
    export let active_tag;
    export let long_desc = "# This is a heading Hello this is Rachel";
    export let active_grid; 
    export let index;


    $: tags_joined = tags.join(" • ")

    let dropdown_visible = false;
    
    // $: console.log(active_tag)

    // sets active to true if the active_tag is in the tags array
    // $: active = active_tag == "" || tags.includes(active_tag)
    // console
    function set_active(x) {
        if (x == "" || x == undefined) {
            return ""
        } else if (tags.includes(x)) {
            return "is-active"
        } else {
            return "is-inactive"
        }
    }
    $: active = set_active(active_tag)

    $: disabled = active == "is-inactive" ? "disabled" : ""

    
    function toggleDropdown() {
        if (active_grid == index) {
            active_grid = -1;
        } else {
            active_grid = index;
        }
    }
    


</script>

<div class="mx-auto my-2 {active} group w-full">
<button on:click={toggleDropdown} class="{disabled} w-full max-w-md">
    <div class="shadow-lg w-full  p-4 group group-[.is-inactive]:blur-sm relative group-[.is-active]:shadow-2xl group-[.is-active]:dark:border-4 focus-within:blur-none  max-w-md hover:shadow-md hover:border-primary-400 ease-in duration-100 h-40 text-left border-solid border-2 rounded-md border-primary-200">
        <h3 class="text-primary-600 dark:text-primary-400  underline group-hover:underline-offset-4 ease-in-out duration-300 forced-colors:block transition appearance-none">{title}</h3>
        <p class="text-primary-500 dark:text-white">{desc}</p>
        <p class="text-primary-400 dark:text-primary-200 transparency:text-sm absolute bottom-5">{tags_joined}</p>
    </div>
</button>

</div>




<style>
    a.disabled {
  pointer-events: none;
  cursor: default;
}
</style>