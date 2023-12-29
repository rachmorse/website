<script>
    export let link;
    export let title;
    export let desc;
    export let tags;
    export let active_tag;

    $: tags_joined = tags.join(" • ")

    
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

    


</script>

<div class="mx-auto my-2 w-full {active} group">
<a href={link}>
    <div class="shadow-lg p-4 group group-[.is-inactive]:blur-sm relative group-[.is-active]:shadow-2xl group-[.is-active]:dark:border-4 focus-within:blur-none mx-auto max-w-md hover:shadow-md hover:border-slate-400 ease-in duration-100 h-40 text-left border-solid border-2 rounded-md border-slate-300">
        <h3 class="text-slate-900 dark:text-slate-200  underline group-hover:underline-offset-4 ease-in-out duration-300 forced-colors:block transition appearance-none">{title}</h3>
        <p class="text-slate-700 dark:text-white">{desc}</p>
        <p class="text-slate-500 text-sm absolute bottom-5">{tags_joined}</p>
    </div>
</a>
</div>

<style>
</style>