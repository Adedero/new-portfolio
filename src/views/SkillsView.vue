<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import 'animate.css'

const popup = ref(null)

const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if(entry.isIntersecting) {
            entry.target.classList.add('animate')
        }
    })
})

/* const secondObserver = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if(entry.isIntersecting) {
            entry.target.classList.add('animate')
        }
    })
})
 */

function showPopup(event) {
    if (event.target.id === "") return
    const rect = event.currentTarget.getBoundingClientRect()
    popup.value.style.top = `${rect.top}px`
    popup.value.style.left = `${rect.left}px`
    popup.value.classList.add('show')
    popup.value.innerText = event.target.id
}

function hidePopup() {
    popup.value.classList.remove('show')
}

onMounted(() => {

   /*  const cardsContainer = document.querySelector('.cards-container')

    secondObserver.observe(cardsContainer) */

    const cards = document.querySelectorAll('.cards-container > .card')

    cards.forEach(card => observer.observe(card))

    cards.forEach(card => card.addEventListener('mouseenter', showPopup))
    cards.forEach(card => card.addEventListener('mouseleave', hidePopup))
})

onUnmounted(() => {
    const cards = document.querySelectorAll('.cards-container > .card')
    cards.forEach(card => card.removeEventListener('mouseenter', showPopup))
    cards.forEach(card => card.removeEventListener('mouseleave', hidePopup))
})
</script>

<template>
    <div class="flex flex-col items-center h-[100%] md:justify-evenly md:pt-16 overflow-y-scroll">
        <h1 class="text-[var(--text)] dark:text-[var(--light)] text-[4rem] font-extrabold self-start md:hidden">skills</h1>

        <p class="text-lg md:px-5 md:text-center">As time goes on, I plan on becoming a <span class="text-2xl">full stack developer.</span> But for now, here's what I got: </p>

        <Teleport to="body">
            <div class="popup bg-zinc-200 font-bold p-1 shadow-md rounded-md cursor-context-menu select-none absolute left-[50%] top-[50%] translate-x-[-50%] translate-y-[-50%] opacity-0 -z-10 transition-all" ref="popup"></div>
        </Teleport>

        <div class="cards-container aspect-square mt-[10%] grid md:mt-0 md:gap-2 lg:gap-8 overflow-y-scroll p-10">
            <div class="card" id="HTML">
                <img src="../assets/icons/html.svg" alt="html" class="w-10 h-10 object-cover">
            </div>
            <div class="card" id="CSS">
                <img src="../assets/icons/css.svg" alt="css" class="w-10 h-10 object-cover">
            </div>
            <div class="card" id="JavaScript">
                <img src="../assets/icons/js.svg" alt="javascript" class="w-10 h-10 object-cover">
            </div>

            <div class="card" id="Tailwind CSS">
                <img src="../assets/icons/tailwind.svg" alt="tailwind" class="w-10 h-10 object-cover">
            </div>

            <div class="center card">
                <svg viewBox="0 0 110.91 61">
                    <g class="fill-[var(--text)] dark:fill-[var(--light)]">
                        <circle cx="97.32" cy="47.41" r="13.59" />
                        <polygon points="18.9 29.98 0 61 37.8 61 18.9 29.98" />
                        <polygon points="25.36 18.83 51.82 61 75.42 61 37.14 0 25.36 18.83" />
                    </g>
                </svg>
            </div>

            <div class="card" id="Bootstrap">
                <img src="../assets/icons/bootstrap.svg" alt="bootstrap" class="w-10 h-10 object-cover">
            </div>

            <div class="card" id="Vue JS">
                <img src="../assets/icons/vue.svg" alt="vue" class="w-10 h-10 object-cover">
            </div>
            <div class="card" id="React JS">
                <img src="../assets/icons/react.svg" alt="react" class="w-10 h-10 object-cover">
            </div>
            <div class="card" id="Node">
                <img src="../assets/icons/node.svg" alt="node" class="w-10 h-10 object-cover">
            </div>
        </div>

        <h1 class="hidden md:block text-red-500 dark:text-lime-500 text-[2rem] font-extrabold">skills</h1>

    </div>
</template>

<style scoped>
.popup.show {
    z-index: 1;
    opacity: 1;
}
.cards-container {
    place-content: center;
    grid-template-columns: repeat(3, 0.5fr);
    
}

.cards-container.animate {
    animation: rotate 2s ease 3s 1;
}

.card {
    @apply bg-zinc-200 dark:bg-slate-800 shadow-md rounded-md aspect-square w-14 grid place-content-center lg:w-16
}
.card {
    transition: filter .3s;
}

.card:hover {
    @apply filter drop-shadow-md
}


.center svg {
    width: 2.5rem;
    transition: 1s;
}

.center.animate svg{
    animation: pulse 0.2s ease 1s 1 forwards;
}

.card.animate:first-of-type {
    opacity: 0;
    animation:
        top-left 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.3s 1 forwards,
        squeeze-top-left 2s ease 3s 1;
}

.card.animate:nth-of-type(2) {
    opacity: 0;
    animation:
        top 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.7s 1 forwards,
        squeeze-top 2s ease 3s 1;
}

.card.animate:nth-of-type(3) {
    opacity: 0;
    animation:
        top-right 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.4s 1 forwards,
        squeeze-top-right 2s ease 3s 1;
}

.card.animate:nth-of-type(4) {
    opacity: 0;
    animation:
        left 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.9s 1 forwards,
        squeeze-left 2s ease 3s 1;
}

.card.animate:nth-of-type(6) {
    opacity: 0;
    animation:
        right 0.5s cubic-bezier(0.23, 1, 0.320, 1) 2s 1 forwards,
        squeeze-right 2s ease 3s 1;

}

.card.animate:nth-of-type(7) {
    opacity: 0;
    animation:
        bottom-left 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.5s 1 forwards,
        squeeze-bottom-left 2s ease 3s 1;
}

.card.animate:nth-of-type(8) {
    opacity: 0;
    animation:
        bottom 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.8s 1 forwards,
        squeeze-bottom 2s ease 3s 1;
}

.card.animate:nth-of-type(9) {
    opacity: 0;
    animation:
        bottom-right 0.5s cubic-bezier(0.23, 1, 0.320, 1) 1.6s 1 forwards,
        squeeze-bottom-right 2s ease 3s 1;
}

@keyframes pulse {
    0% {
        transform: scale(100%);
    }

    50% {
        transform: scale(130%);
    }

    100% {
        transform: scale(100%);
    }
}



@keyframes rotate {
    0% {
        transform: rotate(0deg);
    }

    20% {
        transform: rotate(90deg);
    }

    50% {
        transform: rotate(-90deg);
    }

    100% {
        transform: rotate(1440deg);
    }
}

@keyframes top-left {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(-50%, -50%);
        opacity: 1;
    }
}

@keyframes bottom-left {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(-50%, 50%);
        opacity: 1;
    }
}

@keyframes top-right {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(50%, -50%);
        opacity: 1;
    }
}

@keyframes bottom-right {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(50%, 50%);
        opacity: 1;
    }
}

@keyframes top {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(0, -50%);
        opacity: 1;
    }
}

@keyframes bottom {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(0, 50%);
        opacity: 1;
    }
}

@keyframes left {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(-50%, 0);
        opacity: 1;
    }
}

@keyframes right {
    from {
        transform: translate(0, 0);
        opacity: 0;
    }

    to {
        transform: translate(50%, 0);
        opacity: 1;
    }
}

/* @keyframes squeeze-top-left {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(-25%, -25%);
    }

    80% {
        transform: translate(-25%, -25%);
    }

    100% {
        transform: translate(-50%, -50%);
    }
}

@keyframes squeeze-bottom-left {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(-25%, 25%);
    }

    80% {
        transform: translate(-25%, 25%);
    }

    100% {
        transform: translate(-50%, 50%);
    }
}

@keyframes squeeze-top-right {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(25%, -25%);
    }

    80% {
        transform: translate(25%, -25%);
    }

    100% {
        transform: translate(50%, -50%);
    }
}

@keyframes squeeze-bottom-right {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(25%, 25%);
    }

    80% {
        transform: translate(25%, 25%);
    }

    100% {
        transform: translate(50%, 50%);
    }
}

@keyframes squeeze-top {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(0, -25%);
    }

    80% {
        transform: translate(0, -25%);
    }

    100% {
        transform: translate(0, -50%);
    }
}

@keyframes squeeze-bottom {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(-0, 25%);
    }

    80% {
        transform: translate(0, 25%);
    }

    100% {
        transform: translate(-0, 50%);
    }
}

@keyframes squeeze-left {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(-25%, 0);
    }

    80% {
        transform: translate(-25%, 0);
    }

    100% {
        transform: translate(-50%, 0);
    }
}

@keyframes squeeze-right {
    0% {
        transform: translate(0, 0);
    }

    50% {
        transform: translate(25%, 0);
    }

    80% {
        transform: translate(25%, 0);
    }

    100% {
        transform: translate(50%, 0);
    }
} */
</style>
