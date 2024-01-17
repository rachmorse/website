
<script>
      import { Github, Linkedin, GraduationCap} from "lucide-svelte";
      import "./js/link-xor";
      import Lazy from 'svelte-lazy';

</script>
<div class=" mb-10 mt-24 mx-auto">
<div class="">
    <Lazy height={208}>
        <img class="rounded-full mx-auto h-52" src="headshot.jpg" alt="Dan Hirst">
      </Lazy>
    
    <h1 class="">Rachel Morse</h1>
    <h2>Predoctoral Research Fellow</h2>
    <div class="grid grid-cols-3 max-w-xs mx-auto grid-rows-1 grid-flow-row gap-4 text-center m-5">

      <a href="https://github.com/rachmorse" class="shadow-lg forced-colors:block hover:forced-colors:block p-2 dark:text-primary-400 dark:hover:bg-primary-400 dark:border-primary-400   text-primary-500 hover:bg-primary-500 hover:text-white mx-auto hover:shadow-md ease-in duration-100 text-left border-solid border-2 rounded-md border-primary-500"><Github/></a>
      <a href="https://www.linkedin.com/in/rachel-morse-a803a718b/" class=" shadow-lg dark:text-primary-400 dark:hover:bg-primary-400 dark:border-primary-400 forced-colors:block text-primary-500  p-2  hover:bg-primary-500 hover:text-white mx-auto hover:shadow-md ease-in duration-100 text-left border-solid border-2 rounded-md border-primary-500"><Linkedin/></a>
      <a href="https://scholar.google.co.uk/citations?user=4y0-vQgAAAAJ&hl=en" class=" shadow-lg dark:text-primary-400 dark:hover:bg-primary-400 dark:border-primary-400 forced-colors:block text-primary-500  p-2  hover:bg-primary-500 hover:text-white mx-auto hover:shadow-md ease-in duration-100 text-left border-solid border-2 rounded-md border-primary-500"><GraduationCap/></a>
    </div>
</div>
<h2 class="text-3xl text-center">About</h2>
<p class="text-left p-4">I am a ‘La Caixa’ Fellow pursuing a PhD in neuroscience at the University of Barcelona, where I investigate reserve and resilience in aging. I have a background in psychology and global health that has given me the opportunity to work in child TB in South Africa, cervical cancer in Peru, and dementia prevention in the UK. In my free time, I enjoy being outdoors and hiking in the mountains around Barcelona. </p>
<div class="mx-auto h-auto my-auto m-4">
    <a class="email w-32 text-primary-500 dark:text-primary-400 dark:hover:bg-primary-400 dark:border-primary-400 forced-colors:block p-2 rounded-md shadow-lg appearance-none ease-in duration-100 hover:bg-primary-500  hover:text-white border-solid border-2 border-primary-500" href="79757d78607b2e70777c7d66676024547379757d783a777b79" rel="nofollow, noindex">
        Get in touch
    </a>
</div>
</div>