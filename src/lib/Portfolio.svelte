<script>
    import PortfolioSection from "./PortfolioSection.svelte";
    import {clickOutside} from './js/clickOutside.js';
    import TBApp from "./content/TBApp.svelte";
    import SelfReflection from "./content/SelfReflection.svelte";
    import ScreenTreat from "./content/ScreenTreat.svelte";
    import BreastCancer from "./content/BreastCancer.svelte";
    import FollowUp from "./content/FollowUp.svelte";
    import Stigma from "./content/Stigma.svelte";
    import Ltfu2 from "./content/LTFU2.svelte";
    import rnt from './content/rnt.svelte';
    import appletree from './content/appletree.svelte';


    let projects = [
        {
            title: "Primary-Level Loss to Follow up in Cervical Cancer",
            desc: "Our new cervical cancer program reduced barriers to care, but incomplete registration systems, along with barriers like lack of understanding about HPV, still prevented patients from accessing treatment.",
            tags: ["global health", "cervical cancer", "prevention"],
            long_desc: Ltfu2
        },
        {
            title: "Mental Health & Physical and Cognitive Health",
            desc: "We found that older adults who frequently worry or ruminate report worse physical health and memory. Reducing their negative thinking may help improve overall wellbeing.",
            tags: ["cognitive health", "psychology", "physical health"],
            long_desc: rnt
        },
        {
            title: "Lifestyle Approaches to Dementia Prevention",
            desc: "We found that healthcare professionals believe lifestyle changes can help prevent dementia, but they need guidance and more resources to successfully run these programs.",
            tags: ["dementia", "implementation science", "prevention"],
            long_desc: appletree
        },
        {
            title: "HPV and Cervical Cancer Stigma",
            desc: "Our study found pervasive cervical cancer and HPV stigma that was perpetuated by the community, health care centers, and ministry of health guidelines.",
            tags: ["global health", "cervical cancer", "psychology"],
            long_desc: Stigma
        },
        {
            title: "Hospital-Level Loss to Follow up in Cervical Cancer",
            tags: ["global health", "cervical cancer", "prevention"],
            desc: "Our research revealed that cervical cancer patients want treatment but encounter various financial and logistical obstacles that prevent access to it.",
            long_desc: FollowUp
        },
        {
            title: "Breast Cancer Treatment Experiences",
            tags: ["global health", "breast cancer"],
            desc: "Our research found that women with breast cancer in low-resource settings may need more informational support to help them cope with treatment.",
            long_desc: BreastCancer
        },
        {
            title: "Screen-and-Treat for Cervical Precancer",
            tags: ["global health", "cervical cancer", "prevention"],
            desc: "Our study found that ablative therapy - a type of cervical precancer treatment - may be safe and acceptable for women with HPV",
            long_desc: ScreenTreat
        },
        {
            title: "Self-Reflection and Dementia Risk",
            tags: ["neuroscience", "dementia", "cognitive health"],
            desc: "Our study found that self-reflection may help older adults have better memory and brain health, potentially protecting them from dementia.",
            long_desc: SelfReflection
        },
        {
            title: "A Mobile App for Child TB Treatment",
            tags: ["global health", "tuberculosis", "mobile technology"],
            desc: "Our research proposes using a mobile app to help children in South Africa complete their TB treatment and have a better experience with it.",
            long_desc: TBApp
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
<div>
    <h2 class="text-3xl text-center mt-16 mb-5">Projects</h2>
    <div class="" on:click_outside={() => { active_tag = ""}} use:clickOutside>
        {#each unique_tags as tag}
            <button on:click={set_active_tag} id="{tag}"
                    class="inline-block shadow-lg mx-2 my-1 active:dark:border-primary-500 active:border-primary-400 forced-colors:block hover:forced-colors:block p-2 dark:text-primary-400 dark:hover:bg-primary-400 dark:border-primary-400  text-primary-500 hover:bg-primary-500  hover:text-white mx-auto hover:shadow-md ease-in duration-100 text-left border-solid border-2 rounded-md border-primary-500">{tag}</button>
        {/each}
    </div>
    <PortfolioSection active_tag="{active_tag}" content="{projects}" title="Projects"></PortfolioSection>
</div>

<!-- <PortfolioSection title="Blogs" content="{blogs}" active_tag="{active_tag}"></PortfolioSection> -->
<!-- <PortfolioSection title="Other" content="{other}" active_tag="{active_tag}"></PortfolioSection> -->