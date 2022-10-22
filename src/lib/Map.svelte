<script>
    import { onMount } from "svelte";
    import * as L from "leaflet";
    import 'leaflet/dist/leaflet.css';


    let map;

    onMount(() => {
        map = L.map('map', {'zoomControl': false}).setView([51.511867, -0.110367], 13);
        L.tileLayer(`https://api.os.uk/maps/raster/v1/zxy/Light_3857/{z}/{x}/{y}.png?key=${import.meta.env.VITE_OS_API_KEY}`, {
            attribution: "Contains OS data &copy Crown copyright and database rights 2022"
        }).addTo(map);

    })
</script>
<div id="map" class="w-screen h-screen fixed top-0"></div>