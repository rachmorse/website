<script>

    export let title;
    export let content;
    export let active_tag;
    let active_grid = -1;

    import Project from "./Project.svelte";

    import { afterUpdate, tick } from 'svelte';
    import {cubicInOut} from 'svelte/easing';
    import {slide} from 'svelte/transition';

    let options = {duration: 150, easing: cubicInOut};
    
    // This function means that when someone clicks on a tag, it will scroll to the first project that has that tag.
    afterUpdate(async () => {
        if (!active_tag) return;
        await tick();   // wait until the new card is in the DOM

        document
            .querySelector(`[data-tags*="${active_tag}"]`)   // whole-word match
            ?.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });

    // This function is used to close the an open project card when clicking outside of it.
    function clickOutside(node) {
        const handleClick = event => {
            if (!node.contains(event.target)) {
                active_grid = -1;
            }
        };
        document.addEventListener('mousedown', handleClick, true);

        return {
            destroy() {
                document.removeEventListener('mousedown', handleClick, true);
            }
        };
    }

</script>

<div class="mb-5">
    <div class="grid gap-4 p-4 sm:grid-cols-2 items-stretch h-full justify-center" use:clickOutside>   
            {#each content as { title, desc, link, tags, long_desc }, index}
            <div class="col-span-1 w-full h-full flex flex-col sm:flex-row" data-tags={tags.join(' ')}>
                <Project
                    link="{link}"
                    desc="{desc}"
                    title="{title}"
                    tags="{tags}"
                    active_tag="{active_tag}"
                    bind:active_grid="{active_grid}"
                    index="{index}"
                />
                {#if active_grid == index}
                    <div
                        class="mt-3 sm:hidden rounded-2xl shadow-md border-2 border-primary-200 p-8 w-full max-w-full overflow-x-auto"
                        transition:slide={options}
                    >
                        <article class="prose m-auto">
                            <h1 class="text-primary-300">{title}</h1>
                            <svelte:component this={long_desc} />
                        </article>
                    </div>
                {/if}
            </div>

            {#if index % 2 == 1 || index == content.length - 1}
                {#if active_grid == index || (active_grid % 2 == 0 && active_grid == index - 1)}
                    <div
                        class="mt-3 hidden sm:inline p-12 shadow-md row-start-{Math.floor(index / 2) + 2}
                            rounded-2xl border-2 border-primary-200 w-full sm:col-span-2"
                        transition:slide={options}
                    >
                        <article class="prose m-auto">
                            <h1 class="text-black">{content[active_grid].title}</h1>
                            <svelte:component this={content[active_grid].long_desc} />
                        </article>
                    </div>
                {/if}
            {/if}
        {/each}
    </div>
</div>