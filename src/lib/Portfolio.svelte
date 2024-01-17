<script>
  import PortfolioSection from "./PortfolioSection.svelte";
  import {clickOutside} from './js/clickOutside.js';


    let projects = [
        {
            title: "A Mobile App for Child TB Treatment",
            tags: ["global health","tuberculosis", "mobile technology"],
            desc: "Our research proposes using a mobile app to help children in South Africa complete their TB treatment and have a better experience with it.",
            long_desc: "Children with TB and their caregivers are aware of the importance of treatment, but TB treatment for children is often difficult, with drugs that have an unpleasant tastes and serious side effects. As a result, many children fail to complete their full treatment, despite their initial motivation, and face risk of developing drug resistant TB or serious health complications. In this article, we suggest using a mobile app to improve children’s experience of and adherence to TB treatment in South Africa. Our app suggestion features an avatar, rewards, and social support to address common challenges in TB treatment and improve the well-being of children and their caregivers throughout the process."
        },
        {
            title: "Self-Reflection and Dementia Risk",
            tags: ["neuroscience", "dementia", "neuroimaging"],
            desc: "Our study found that self-reflection may help older adults have better memory and brain health, potentially protecting them from dementia.",
            long_desc: "Dementia is a devastating disease that affects over 50 million people worldwide. However, up to one third of cases can be prevented by addressing modifiable risk factors, such as poor diet and lack of physical activity. Psychological factors that may increase dementia risk have received less attention. This study examined one of them, self-reflection, which involves actively assessing your own thoughts, feelings, and behaviors. We found that older adults who engaged in more self-reflection had better memory performance and higher glucose metabolism. These factors are both protective against Alzheimer’s disease, the most common form of dementia."        
        },
        {
            title: "Screen-and-Treat for Cervical Precancer",
            tags: ["global health", "cervical cancer", "qualitative"],
            desc: "Our study found that ablative therapy - a type of cervical precancer treatment - may be a safe and acceptable for women with HPV",
            long_desc: "An HPV based screen-and-treat approach with ablative therapy can prevent cervical cancer. Patients who test positive for HPV, the cause of cervical cancer, can receive ablative therapy treatment at a clinic on the same day. The WHO recommends this approach, but ablative therapy is new and, though it is safe, the experience patients receive this treatment is not well understood. In this study, we aimed to understand whether patients found ablative therapy treatment acceptable and feasible. We found that, although patients experienced minor side effects, they experienced satisfaction and relief, and wanted this treatment to be available at more clinics."        
        },
        {
            title: "Breast Cancer Treatment Experiences",
            tags: ["global health", "breast cancer", "qualitative"],
            desc: "Our research found that women with breast cancer in low-resource settings may need more informational support to help them cope with treatment.",
            long_desc: "Breast cancer is the most common cause of cancer-related death in Peru, and its treatment is physically and emotionally demanding. In this study, we wanted to understand how women in Peru cope with breast cancer treatment and what support they need. We found that women lacked information about breast cancer and its treatment and wanted more guidance from health professionals. Women also experienced many challenging emotions that could be supported by social support groups; however, not all women had access to these groups, and instead relied on friends and family for support. We suggest that breast cancer programs provide more informational support to help women cope with breast cancer treatment."
        },
        {
            title: "Loss to Follow up in Cervical Cancer",
            tags: ["global health", "cervical cancer", "qualitative"],
            desc: "Our research revealed that cervical cancer patients want treatment but encounter various financial and logistical obstacles that prevent access to it.",
            long_desc: "In many cervical cancer prevention programs, patients with positive screening results are referred to the hospital for additional tests and treatment. However, in the Amazonian region of Peru, 70% of patients referred to the hospital were not receiving the care they needed. In this study, we set out to understand why so many patients were not able to receive care. We found that, while patients were strongly motivated, they encountered many challenges. One main challenge was an inadequate registration system where there was often no information about each patients’ care. Other challenges were structural, such as long wait times or doctor strikes. Others were financial, including high cost of travel to the hospital, and others were cognitive, such as not receiving clear information from healthcare providers. We suggest that cervical cancer programs focus on addressing these barriers."
        },
        {
            title: "HPV and Cervical Cancer Stigma",
            desc: "Our study found pervasive cervical cancer and HPV stigma that was perpetuated by the community, health care centers, and ministry of health guidelines.",
            tags: ["global health", "cervical cancer", "stigma", "qualitative"],
            long_desc: "HPV is a common sexually transmitted disease that can develop into cervical cancer. Most women will get an HPV infection in their lifetime that their bodies will be able control. However, in some cases, women will need treatment to help prevent HPV from developing into cervical cancer. An HPV infection can come from any past sexual partner, even if a woman has been in a monogamous relationship for a long time. Despite how common HPV is, HPV and cervical cancer are often stigmatized. In this study, we aimed to understand this stigma and explore its impact. We conducted our research in a low-resource setting in Peru and found widespread stigma where HPV was considered a shameful and secretive disease. The stigma blamed women for being promiscuous or men for being unfaithful, and was reinforced by patients, community members, healthcare workers and policies. This stigma sometimes stopped women from getting screened for HPV. We propose that cervical cancer prevention programs address stigma throughout the healthcare system and, instead of focusing on associations between HPV and sexual behaviors, provide comprehensive information about HPV and offer screening to all eligible women, regardless of sexual history."
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