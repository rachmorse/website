<script>
    import Card from "./Card.svelte";

    export let current = "code";

    const code = [{
            title: "osdatahub Python",
            desc: "Open source Python package for the OS Data Hub",
            link: "https://github.com/OrdnanceSurvey/osdatahub",
            image: "python.png",
            alt: "Python logo",
            fit: "object-contain"

        },
        {
            title: "osdatahub JavaScript",
            desc: "Open source Node package for the OS Data Hub",
            link: "https://github.com/OrdnanceSurvey/osdatahub-js",
            image: "javascript.png",
            alt: "JavaScript code"
        },
        {
            title: "Pret Crawl",
            desc: "All hail the Pret Crawl",
            link: "https://www.pretcrawl.com",
            image: "coffee.png",
            alt: "Coffee"
        },
        {
            title: "Country-A-Like",
            desc: "Website that determines which country looks like a given image",
            link: "https://dchirst-what-country-am-i-main-nkgm6x.streamlitapp.com/",
            image: "country-a-like.png",
            alt: "Screenshot of Country-a-like website",
            fit: "object-contain"

        },
        {
            title: "Space Company Name Generator",
            desc: "Make your own space company in 1 easy step",
            link: "https://danhirst98.github.io/space_company_generator/",
            image: "spacename.png",
            alt: "Space Name Generator screenshot",
            fit: "object-contain"
        },
        {
            title: "SAR Activity Monitor",
            desc: "Using SAR satellite imagery to monitor the activity of smelters",
            link: "https://danielhirst1998.users.earthengine.app/view/guixi-poc",
            image: "copper.avif",
            alt: "Copper"
        }

    ]

    const blogs = [
        {
            title: "Peat Health Index",
            desc: "ArcGIS StoryMap about EO presented at COP26",
            link: "https://storymaps.arcgis.com/stories/68ac541504fc4714b371b1a33e540c95",
            image: "peat.png",
            alt: "Peatlands"
        },
        {
            title: "Get Pret Go",
            desc: "How to walk through London always with a coffee in your hand",
            link: "https://python.plainenglish.io/get-pret-go-a-geospatial-project-966ad04f5fb9",
            image: "coffee.png",
            alt: "Coffee"
        },
        {
            title: "OS Data Hub OAuth API",
            desc: "How to securely use the OS Data Hub with OAuth",
            link: "https://github.com/dchirst/osdatahub-oauth-blogpost",
            image: "map.png",
            alt: "Map of Newcastle"
        },
        {
            title: "London's Blue Plaques",
            desc: "Spatial analysis of London's Blue Plaques",
            link: "https://python.plainenglish.io/finding-the-densest-area-of-londons-blue-plaques-with-geospatial-data-f5559ebfef21",
            image: "plaque.png",
            alt: "Blue Plaque of Alan Turing"
        },
        {
            title: "Vector Data in Python",
            desc: "Blog post about easily showing points, lines, and polygons on maps",
            link: "https://python.plainenglish.io/how-to-easily-display-vector-geospatial-data-in-python-c739482c395",
            image: "vector.png",
            alt: "Open Street Map vector"
        },
        {
            title: "Open Source Coding",
            desc: "Blog detailing our first expedition into open-source software development",
            link: "https://python.plainenglish.io/our-first-expedition-into-open-source-coding-d62810453d3c",
            image: "code.png",
            alt: "Code"
        }
    ]

    const other = [
        {
            title: "Chapel Thrill Escapes",
            desc: "Non-profit escape room company",
            link: "https://www.chapelthrillescapes.com/",
            image: "chapelthrill.png",
            alt: "Chapel Thrill Escapes logo",
            fit: "object-contain"

        },
        {
            title: "Prospero Space Fellowship",
            desc: "Internships, mentorships, and retreats for students",
            link: "https://prosperofellowship.org/",
            image: "prospero.png",
            alt: "Prospero Space Fellowship logo",
            fit: "object-contain"
        }
    ]

    const portfolios = {
        code: code,
        blogs: blogs,
        other: other
    }

    $: currentPortfolio = portfolios[current]
</script>

<div class="carousel mx-5 md:w-3/4 md:m-auto md:h-64 h-96 ">
    {#each currentPortfolio as content }
        <Card {...content}/>
    {/each}
</div>


