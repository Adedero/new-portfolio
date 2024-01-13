<script setup>
import SkillsView from './SkillsView.vue';
</script>

<template>
    <div class="about-header relative h-full overflow-y-scroll">
        <div class="flex items-center justify-between flex-wrap">
            <h1 class="relative about-heading text-[3.5rem] font-extrabold text-5[rem] md:block">About me<span class="text-red-500 dark:text-lime-500">.</span></h1>
            

            <a href="../../public/adedero-resume.pdf" download class="relative p-2 px-4 text-sm hover:text-[var(--light)] hover:bg-[var(--text)] font-bold border border-[var(--dark)] dark:border-[var(--light)]  rounded-full translate-y-2 transition-colors z-10">Download CV</a>
        </div>

        <div class="about-text overflow-y-scroll pt-6">
            <p class="text-lg">
                I'm a front-end developer on a mission to make the web a more enchanting place. <span class="text-2xl">With over 4 years of experience, I've transformed coffee-fueled ideas into dazzling digital experiences.</span> I don't just write code; I compose symphonies of pixels that dance and sing on the screen.<br><br>

                What fuels my code engine? <span class="text-2xl"> Passion, curiosity, and an insatiable appetite for innovation.</span>  I believe in pushing boundaries, experimenting with the latest tech trends, and turning challenges into opportunities for growth. <br><br>

                Collaboration is my secret sauce. <span class="text-2xl">I thrive in dynamic teams, where creativity sparks, and brilliant ideas collide.</span> The more minds, the merrier! <br><br>

                Outside the tech realm, you might catch me exploring design galaxies, <span class="text-2xl">debating the future of front-end at meetups,</span> or simply sipping on a cup of inspiration from design blogs. ☕
            </p>
        </div>  
    </div>

    <div class="hidden md:block">
        <SkillsView />
    </div>

    
</template>

<style scoped>
.about-header::before {
    @apply content-[""] absolute w-52 h-52 rounded-full  bg-slate-500 bg-opacity-40 dark:bg-opacity-30 left-0 top-0
}

.about-header::after {
    @apply content-[""] absolute w-52 h-52 bg-red-500 dark:bg-lime-500 dark:bg-opacity-10 bg-opacity-10 right-0 bottom-0 -z-0
}

.about-header::before {
    animation: move-before 20s infinite ease forwards;
}

.about-header::after {
    animation: move-after 20s infinite ease forwards;
}


.about-text {
    max-height: calc(100dvh - 11.5rem)
}

@keyframes move-before {
    0% { translate: 0 }
    25% { translate: 95% 95% }
    50% { translate: 0% 95%}
    75% { translate: 95% 0 }
    100% { translate: 0;}
}

@keyframes move-after {
    0% { translate: 0 }
    25% { translate: -95% -95% }
    50% { translate: 0 -95%}
    75% { translate: -95% 0 }
    100% { translate: 0;}
}
</style>