<script>
    import { tweened } from "svelte/motion";
    import { cubicOut } from 'svelte/easing'

    import { flip } from 'svelte/animate';

    function move(x, y) { return `transform: translate(${x}px, ${y}px)` }
    let x = tweened(0, {easing: cubicOut})
    let y = tweened(0, {easing: cubicOut})

    function setValue() {
        x.set(Math.random() * 1000)
        y.set(Math.random() * 1000)
    }
</script>

<div class="css-selector w-screen h-screen bg-black">

</div>



<style>
    div {
        background: radial-gradient(
                circle at top left,
                rgba(176, 64, 64, 0.5),
                transparent 400px
        ),
        radial-gradient(
                circle at top right,
                rgba(111, 168, 73, 0.5),
                transparent 400px
        ),
        radial-gradient(
                at bottom left,
                rgba(255, 0, 255, 0.5),
                transparent 400px
        ),
        radial-gradient(
                at bottom right,
                rgba(255, 100, 100, 0.5),
                transparent 400px
        );
    }

    .css-selector {
    background: linear-gradient(334deg, #00e4aa, #2bbd00, #dbd716, #f5008b, #f5008b);
    background-size: 1000% 1000%;

    -webkit-animation: AnimationName 22s ease infinite;
    -moz-animation: AnimationName 22s ease infinite;
    animation: AnimationName 22s ease infinite;
    }

    @-webkit-keyframes AnimationName {
        0%{background-position:50% 0%}
        50%{background-position:51% 100%}
        100%{background-position:50% 0%}
    }
    @-moz-keyframes AnimationName {
        0%{background-position:50% 0%}
        50%{background-position:51% 100%}
        100%{background-position:50% 0%}
    }
    @keyframes AnimationName {
        0%{background-position:50% 0%}
        50%{background-position:51% 100%}
        100%{background-position:50% 0%}
    }
</style>