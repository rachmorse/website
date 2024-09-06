<script>
    import Lazy from "svelte-lazy"
</script>
<div class="text-left dark:text-white">
    <p>While cognitive and physical health are often seen as separate, they are closely related, especially as we age. 
        Understanding what affects both can help in developing better interventions for healthy aging. Here we explored how 
        worry and rumination—persistent negative thoughts—affect the physical and cognitive health of older adults. </p>
    <p>We found that increased worry and rumination were not significantly associated with objective health measures; however, 
        they were associated with poorer subjective physical and cognitive health, meaning older adults who engaged in negative 
        thinking tended to report having poorer health. Developing interventions that target these negative thinking styles may 
        improve how older adults feel and function in daily life, ultimately supporting healthier aging. </p>
    
        <hr style="width: 100%; height: 2px; margin: 10px auto 30px; background-color: white; border: none;">

    <h4 style="text-align: center; margin-bottom: 5px;">Results Summary</h4>
    <hr style="width: 22.5%; height: 2px; margin: 5px auto 5px; background-color: lightgrey; border: none;">
    <p style="margin: 0; line-height: 1.2;"><small>
        This figure depicts the significant results of our research on worry and rumination and their 
        relationship with subjective cognitive and physical health.
    </small></p> 
    <Lazy>
        <img alt="rnt findings" src="rnt findings.png"/>

        <h4 style="text-align: center; margin-bottom: 5px;">Worry and Rumination & Subjective Health</h4>
        <hr style="width: 56%; height: 2px; margin: 5px auto 5px; background-color: lightgrey; border: none;">
        <p style="margin: 0; line-height: 1.2;"><small>
            These figures show the relationship between worry and rumination and subjective health.
            The top figures show that as worry and rumination increase perceived physical health decreases. 
            The bottom figures show that as worry and rumination increase so do perceived cognitive difficulties, such as poorer memory.       
        </small></p> 
        <a href="rnt graphs.jpeg" target="_blank" rel="noreferrer">
            <img alt="rnt graphs" src="rnt graphs.jpeg"/>
        </a>
    </Lazy>
    
    <h4 style="text-align: center; margin-bottom: 5px;">Analysis Code</h4>
    <hr style="width: 18%; height: 2px; margin: 5px auto 5px; background-color: lightgrey; border: none;">
    <p>All of the analysis code for this project is available <a class="text-primary-500 dark:text-primary-200"
        href="https://github.com/rachmorse/Worry-Rumination-and-Older-Adult-Health" rel="noreferrer" target="_blank">here</a> for openess and transparency.</p>
    
    <h4 style="text-align: center; margin-bottom: 5px;">Reference</h4>
    <hr style="width: 14%; height: 2px; margin: 5px auto 5px; background-color: lightgrey; border: none;">
    <p><strong class="dark:text-white">Morse, R. M.†</strong>, Koutsoubelis, F.†, Whitfield, T., […], Marchant, N. L., & for the Medit-Ageing Research Group 
        “Worry and ruminative brooding: associations with cognitive and physical health in older adults.” Frontiers in Psychology. <a class="text-primary-500 dark:text-primary-200"
                           href="https://doi.org/10.3389/fpsyg.2024.1332398" rel="noreferrer" target="_blank">https://doi.org/10.3389/fpsyg.2024.1332398</a>
    </p>
    <p><small>† denotes coauthorship</small></p>
</div>