<script setup>
import FbIcon from '@/components/FbIcon.vue';
import GhIcon from '@/components/GhIcon.vue';
import InIcon from '@/components/InIcon.vue';
import 'animate.css'
</script>

<template>
    <div class="h-full flex flex-col justify-between md:justify-center md:w-1/2 relative">
        <h1 class="hero-text text-[3.5rem] text-center font-extrabold md:hidden animate__animated animate__fadeInDown amimate__fast">Hi, <br> I'm Dero<span class="text-red-500 dark:text-lime-500">.</span>
        </h1>

        <h1 class="hidden hero-text relative text-[4rem] font-extrabold text-5[rem] md:block lg:text-[5.5rem] animate__animated animate__fadeInDown amimate__fast">Hi, <br> I
            <span class="absolute top-10 left-[1.25rem] lg:top-10 lg:left-[1.7rem]">,</span>
            m Dero
        </h1>

        <div class="img-container w-[16rem] mx-auto relative md:hidden animate__animated animate__fadeInRight animate__fast animate__delay-1s">
            <img class="my-pic w-60 h-60 object-cover z-10 rounded-xl relative dark:filter dark:grayscale" src="../assets/images/me.png" alt="adedero_pic">
        </div>

        <p class="desc text-xl dark:font-[300] pt-8 text-center px-5 md:text-left md:px-0 md:text-2xl lg:pr-24 animate__animated animate__fadeInUp amimate__fast animate__delay-1s">
            Front end developer dedicated to making your designs a picture perfect reality. <br> If you can think it, I can build it!
        </p>

        <div class="flex items-center justify-center md:justify-normal gap-5 md:pt-5 animate__animated animate__fadeInLeft amimate__fast animate__delay-1s">
            <button class="py-2 px-10 border-2 font-bold text-sm border-[var(--text)] dark:border-[var(--light)] rounded-full hover:bg-[var(--text)] hover:text-[var(--light)] transition-colors">Hire me</button>
            <button class="text-red-500 dark:text-lime-500 font-bold text-sm hover:underline">Learn more</button>
        </div>

        <div class="absolute right-0 top-[36%] flex flex-col items-center justify-center gap-6 pt-2 md:justify-start md:relative md:top-0 md:pt-5 md:flex-row lg:pt-12 animate__animated animate__fadeInUp amimate__fast animate__delay-1s">
            <a href="#">
                <FbIcon />
            </a>
            <a href="#">
                <GhIcon />
            </a>
            <a href="#">
                <InIcon />
            </a>
        </div>
    </div>

    <div class="hidden md:grid md:justify-end md:pr-10 md:w-1/2">
        <div class="img-container w-72 lg:w-full justify-self-end relative mr-5 animate__animated animate__zoomIn">
            <img class="my-pic-2 w-72 lg:w-full lg:h-[30rem] lg:object-cover z-10 rounded-xl relative dark:filter dark:grayscale animate__animated animate__fadeInUp amimate__fast animate__delay-1s" src="../assets/images/me.png" alt="adedero_pic">
        </div>
    </div>
</template>

<style scoped>
.hero-text {
    line-height: 5rem;
}

.img-container {
    --animate-delay: 0.5s;
}
.img-container::before {
    @apply content-[""] absolute w-full h-full border-[0.5px] border-[var(--dark)] -right-6 -bottom-6 rounded-xl dark:border-[var(--light)] md:-left-4 md:-right-0 md:-top-4 lg:w-[100%] lg:-left-6 lg:-top-6
}

.img-container::after {
    @apply hidden content-[""] absolute w-32 h-32 border-[0.5px] border-[var(--dark)] -right-8 -bottom-8 rounded-full dark:border-[var(--light)] md:block lg:-bottom-8 lg:-right-[10%] lg:w-40 lg:h-40
}


@media screen and (min-width: 1024px) {
    .hero-text {
        line-height: 6rem;
    }

    .desc {
        line-height: 2.5rem;
    }
    
}
</style>