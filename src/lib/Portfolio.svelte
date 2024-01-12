<script>
  import PortfolioSection from "./PortfolioSection.svelte";
  import {clickOutside} from './js/clickOutside.js';


    let projects = [
        {
            title: "A Mobile App for Child TB Treatment",
            tags: ["global health","tuberculosis", "mobile technology"],
            desc: "Our research proposes using a mobile app to help children in South Africa complete their TB treatment and have a better experience with it.",
            long_desc: "Children with TB and their caregivers are aware of the importance of treatment, but TB treatment for children is often difficult, with drugs that have an unpleasant taste and serious side effects. As a result, many children fail to complete their full treatment, despite their initial motivation, and face the risk of developing drug resistant TB or even death. In this article, we suggest using a mobile app to enhance children’s experience of and adherence to TB treatment in South Africa. Our app features an avatar, rewards, and social support to address common challenges in TB treatment and improve the well-being of children and their caregivers throughout the treatment process."
        },
        {
            title: "Self-Reflection and Dementia Risk",
            tags: ["neuroscience", "dementia", "neuroimaging"],
            desc: "Our study found that self-reflection may help older adults have better memory and brain health, potentially protecting them from dementia.",
            long_desc: "Dementia is a devastating disease that affects over 50 million people worldwide. However, up to one third of cases can be prevented by addressing modifiable lifestyle risk factors, such as poor diet and lack of physical activity. Psychological factors that may increase dementia risk have received less attention. This study examined one of them: self-reflection, which involves actively assessing one’s own thoughts, feelings, and behaviors. We found that older adults who engaged in more self-reflection had better memory performance and higher glucose metabolism. These factors are both protective against Alzheimer’s disease, the most common form of dementia."
        },
        {
            title: "Screen-and-Treat for Cervical Precancer",
            tags: ["global health", "cervical cancer", "qualitative"],
            desc: "Our study found that ablative therapy - a type of cervical precancer treatment - may be a safe and acceptable for women with HPV",
            long_desc: "Preventing cervical cancer in remote, low-resource settings can face challenges related to getting equipment to appropriate places. An HPV-based screen-and-treat approach with ablative therapy aims to address many of these challenges. We aimed to understand whether the recipients of these treatment approaches – women – find the treatment acceptable, and found that while women experienced minor side effects with the treatment, they expressed satisfaction and relief that they were able to receive ablative therapy treatment."
        },
        {
            title: "Breast Cancer Treatment Experiences",
            tags: ["global health", "breast cancer", "qualitative"],
            desc: "Our research found that women with breast cancer in low-resource settings may need more informational support to help them cope with treatment.",
        },
        {
            title: "Loss to Follow up in Cervical Cancer",
            tags: ["global health", "cervical cancer", "qualitative"],
            desc: "Our research revealed that cervical cancer patients want treatment but encounter various financial and logistical obstacles that prevent access to it.",
        },
        {
            title: "HPV and Cervical Cancer Stigma",
            desc: "Our study found pervasive cervical cancer and HPV stigma that was perpetuated by the community, health care centers, and ministry of health guidelines.",
            tags: ["global health", "cervical cancer", "stigma", "qualitative"]
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