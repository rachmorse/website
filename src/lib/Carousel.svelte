<script>
    import Card from "./Card.svelte";

    export let current;

    const code = [{
            title: "osdatahub Python",
            desc: "Open source Python package for the OS Data Hub",
            link: "https://github.com/OrdnanceSurvey/osdatahub",
            image: ""
        },
        {
            title: "osdatahub JavaScript",
            desc: "Open source Node package for the OS Data Hub",
            link: "https://github.com/OrdnanceSurvey/osdatahub-js",
            image: ""
        },
        {
            title: "Pret Crawl",
            desc: "All hail the Pret Crawl",
            link: "www.pretcrawl.com",
            image: "",
        },
        {
            title: "Country-A-Like",
            desc: "Website that determines which country looks like a given image",
            link: "https://dchirst-what-country-am-i-main-nkgm6x.streamlitapp.com/",
            image: ""
        }

    ]

    const blogs = [
        {
            title: "Peat Health Index",
            desc: "ArcGIS StoryMap about EO presented at COP26",
            link: "",
            image: ""
        },
        {
            title: "Get Pret Go",
            desc: "How to walk through London always with a coffee in your hand",
            link: "https://python.plainenglish.io/get-pret-go-a-geospatial-project-966ad04f5fb9"
        },
        {
            title: "OS Data Hub OAuth API",
            desc: "How to use the OAuth API to securely use the OS Data Hub in websites",
            link: "https://github.com/dchirst/osdatahub-oauth-blogpost"
        },
        {
            title: "London's Blue Plaques",
            desc: "Spatial analysis of London's Blue Plaques",
            link: "https://python.plainenglish.io/finding-the-densest-area-of-londons-blue-plaques-with-geospatial-data-f5559ebfef21"
        },
        {
            title: "Vector Data in Python",
            desc: "Blog post about easily showing points, lines, and polygons on maps",
            link: "https://python.plainenglish.io/how-to-easily-display-vector-geospatial-data-in-python-c739482c395"
        },
        {
            title: "Open Source Coding",
            desc: "Blog detailing our first expedition into open-source software development",
            link: "https://python.plainenglish.io/our-first-expedition-into-open-source-coding-d62810453d3c"
        }
    ]

    const other = [

    ]

    const portfolios = {
        code: code,
        blogs: blogs,
        other: other
    }

    $: currentPortfolio = portfolios[current]
</script>

<div class="carousel w-3/4 m-auto h-64">
    {#each currentPortfolio as content }
        <Card {...content}/>
    {/each}
</div>


