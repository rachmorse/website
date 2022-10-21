<script>
    import { onMount } from "svelte";
    import * as L from "leaflet";

    let map;

    onMount(() => {
        map = L.map('map').setView([51.511867, -0.110367], 13);
        L.tileLayer(`https://api.os.uk/maps/raster/v1/zxy/Light_3857/{z}/{x}/{y}.png?key=${import.meta.env.VITE_OS_API_KEY}`, {
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);

    })
</script>
<div id="map" class="w-screen h-screen"></div>