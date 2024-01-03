<script>
  import PortfolioSection from "./PortfolioSection.svelte";
  import {clickOutside} from './js/clickOutside.js';


    let projects = [
        {
            title: "How an App Can Support Child Tuberculosis Treatment",
            tags: ["mobile technology", "tuberculosis", "global health"],
            long_desc: "Tuberculosis treatment for children is often challenging, with unpleasant drugs that cause serious side effects. In this article, we propose using a mobile app to improve children’s experience of and adherence to tuberculosis treatment, based on our research in South Africa."
        },
        {
            title: "How Self-reflection Relates to Indicators of Alzheimer's",
            tags: ["neuroscience", "alzheimer’s disease", "neuroimaging"],
            long_desc: "We found that self-reflection was linked to better memory performance and higher brain activity, but not to lower levels of amyloid, a protein that accumulates in the brain and associated with Alzheimer’s."
        },
        {
            title: "Using ablative therapy to prevent cervical cancer",
            tags: ["Cervical cancer", "women’s sexual health", "global health", "qualitative"],
            long_desc: "Preventing cervical cancer in remote, low-resource settings can face challenges related to getting equipment to appropriate places. An HPV-based screen-and-treat approach with ablative therapy aims to address many of these challenges. We aimed to understand whether the recipients of these treatment approaches – women – find the treatment acceptable, and found that while women experienced minor side effects with the treatment, they expressed satisfaction and relief that they were able to receive ablative therapy treatment."
        },
        {
            title: "Improving Breast Cancer Treatment",
            tags: ["breast cancer", "global health", "qualitative"],
        },
        {
            title: "Decreasing rates of loss to follow up in cervical cancer prevention and treatment",
            tags: ["cervical cancer", "women’s sexual health", "global health", "qualitative"]
        },
        {

            title: "HPV and cervical cancer stigma",
            tags: ["cervical cancer", "women’s sexual health", "stigma", "global health"]
        }
    ]
      
    let tags = [...projects] 
          .map(x => x.tags)
          .flat();
      let unique_tags = [...new Set(tags)];

      let active_tag = "";
  
      function set_active_tag(event) {
        let tag_id = event.target.id;
        if (active_tag == tag_id) {
          active_tag = "";
        } else {
          active_tag = tag_id;
        }
      }

</script>

<div use:clickOutside on:click_outside={() => { active_tag = ""}} class="mb-5">
  {#each unique_tags as tag}
  <button on:click={set_active_tag} id="{tag}" class="inline-block shadow-lg mx-2 my-1 active:dark:border-primary-500 active:border-primary-400 forced-colors:block hover:forced-colors:block p-2 dark:text-primary-400 dark:hover:bg-primary-400 dark:border-primary-400  text-primary-500 hover:bg-primary-500  hover:text-white mx-auto hover:shadow-md ease-in duration-100 text-left border-solid border-2 rounded-md border-primary-500">{tag}</button>
  {/each}
</div>


<PortfolioSection title="Projects" content="{projects}" active_tag="{active_tag}"></PortfolioSection>
<!-- <PortfolioSection title="Blogs" content="{blogs}" active_tag="{active_tag}"></PortfolioSection> -->
<!-- <PortfolioSection title="Other" content="{other}" active_tag="{active_tag}"></PortfolioSection> -->