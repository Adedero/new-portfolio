<script setup>
const emits = defineEmits([ 'on-skip' ])
</script>

<template>
    <header class="flex items-center justify-between p-4">
        <div class="flex gap-3 w-20">
            <div class="w-4 h-4 bg-[#FE6055] rounded-full"></div>
            <div class="w-4 h-4 bg-[#FFC223] rounded-full"></div>
            <div class="w-4 h-4 bg-[#21CD45] rounded-full"></div>
        </div>
        <p class="text-white">adedero</p>
        <div class="w-20"></div>
    </header>
    
    <div class="px-4 text-white">
        <button type="button" class="hover:text-sky-300" @click="$emit('on-skip')"> >> Skip</button>
    </div>

    <section class="p-4 flex flex-col justify-evenly whitespace-nowrap h-56 overflow-y-scroll">
        <div class="flex gap-3">
            <span class="text-gray-500">$ </span>
            <p class="code code1">
                <span class="text-lime-400">name</span>
                <span class="text-white">: </span>
                <span class="text-sky-300">adedero cosmos</span>
            </p>
        </div>

        <div>
            <p class="code code2">
                <span class="text-gray-500">$ </span>
                <span class="text-lime-400">profession</span>
                <span class="text-white">: </span>
                <span class="text-sky-300">front-end developer</span>
            </p>
        </div>

        <div>
            <p class="code code3">
                <span class="text-gray-500">$ </span>
                <span class="text-lime-400">skills</span>
                <span class="text-white">: [ </span>
                <span class="text-sky-300">html, css, javascript, vue...
                    <span class="text-white">]</span>
                </span>
            </p>
        </div>

        <div>
            <p class="code code4 text-white">
                <span class="text-gray-500">$ </span>
                <span>npm run dev</span>
            </p>
        </div>

        <div>
            <p class="code code5 text-white flex items-center gap-2" >
                <span class="text-gray-500">$</span>
                <span class="outline-none" id="content" contenteditable="true"></span>
            </p>
        </div>
    </section>
</template>

<style scoped>

@keyframes typewriter{ from{width: 0;} to{width: 20rem;} }

@keyframes blinkTextCursor{
    from{border-right-color: transparent;}
    to{border-right-color: transparent;}
    50%{border-right-color: rgba(255,255,255);}
}

.code {
    white-space: nowrap;
    overflow: hidden;
    border-right: 5px solid rgba(255,255,255);
    height: 1.25rem;
}


@keyframes typewriter1{ from{width: 0;} to{width: 13rem;} }

.code1 {
    animation:
        typewriter1 1.5s steps(25) .5s 1 both,
        blinkTextCursor 500ms steps(94) 5 normal forwards;
}


@keyframes typewriter2 { from{width: 0;} to{width: 21rem;} }

.code2 {
    animation:
        typewriter2 2s steps(35) 3s 1 both,
        blinkTextCursor 500ms steps(44) 2.6s 6 normal both;
}

@keyframes typewriter3 { from{width: 0;} to{width: 27rem;} }

.code3 {
    animation:
        typewriter3 2.5s steps(55) 6s 1  normal both,
        blinkTextCursor 500ms steps(44) 5.5s 7 normal both;
}

@keyframes typewriter4 { from{width: 0;} to{width: 8.5rem;} }

.code4 {
    animation:
        typewriter4 1s steps(12) 9.3s 1  normal both,
        blinkTextCursor 500ms steps(44) 9s 3 normal both;
}


@keyframes typewriter5 { from{visibility: hidden;} to{visibility: visible} }
.code5 {
    border-right-color: transparent;
    animation: typewriter5 1s 11s 1  normal both;   
}

.code5 #content {
    border-right: 5px solid rgba(255,255,255);
    border-right-color: transparent;
    animation: blinkTextCursor 500ms 11s infinite
}
</style>
