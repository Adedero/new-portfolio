<script setup>
import FbIcon from '@/components/FbIcon.vue';
import GhIcon from '@/components/GhIcon.vue';
import InIcon from '@/components/InIcon.vue';
</script>

<template>
    <div class="h-full flex flex-col justify-between md:justify-center md:w-1/2">
        <h1 class="hero-text relative text-[4rem] font-extrabold md:text-5[rem] lg:text-[5.5rem] animate__animated animate__fadeInDown amimate__fast">Hi, <br> I
            <span class="absolute top-10 left-5 lg:top-10 lg:left-[1.7rem]">,</span>
            m Dero
        </h1>

        <div class="img-container w-[16rem] relative md:hidden animate__animated animate__fadeInRight animate__fast animate__delay-1s">
            <img class="my-pic w-72 z-10 rounded-xl relative dark:filter dark:grayscale" src="../assets/images/my_pic.jpg" alt="adedero_pic">
        </div>

        <p class="desc text-xl dark:font-[300] pt-8 pr-24 md:pr-0 md:text-2xl lg:pr-24 animate__animated animate__fadeInUp amimate__fast animate__delay-1s">
            Front end developer dedicated to making your designs a picture perfect reality. If you can think it, I can build it!
        </p>

        <div class="flex items-center gap-6 pt-2 md:pt-11 lg:pt-12 animate__animated animate__fadeInUp amimate__fast animate__delay-1s">
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
        <div class="img-container w-72 lg:w-[80%] justify-self-end relative mr-5">
            <img class="my-pic w-72 lg:w-[90%] lg:h-[30rem] lg:object-cover z-10 rounded-xl relative dark:filter dark:grayscale" src="../assets/images/my_pic.jpg" alt="adedero_pic">
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
    @apply content-[""] absolute w-full h-full border-[0.5px] border-[var(--dark)] -right-6 -bottom-6 rounded-xl dark:border-[var(--light)] md:-left-4 md:-right-0 md:-top-4 lg:w-[80%] lg:-left-6 lg:-top-6
}

.img-container::after {
    @apply hidden content-[""] absolute w-32 h-32 border-[0.5px] border-[var(--dark)] -right-8 -bottom-8 rounded-full dark:border-[var(--light)] md:block lg:-bottom-8 lg:right-[0%] lg:w-40 lg:h-40
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