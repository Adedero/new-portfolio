<template>
     <header class="w-full flex flex-col font-[500] text-xs lg:text-sm cursor-context-menu">
        <div class="bg-[#1C89FA] dark:bg-gray-600 p-1 lg:px-2 text-white flex items-center justify-between">
            <div class="flex items-center gap-1">
                <span class="material-symbols-rounded text-xl">apps</span>
                <p>Word</p>
            </div>

            <div>
                About Me
            </div>

            <div>
                Adedero Cosmos
            </div>
        </div>

        <div class="flex items-center justify-between p-1 bg-[#F4F4F4]">
            <ul class="flex gap-3 lg:gap-5">
                <li class="cursor-pointer">File</li>
                <li class="active-list before:bg-[#1C89FA] cursor-pointer">Home</li>
                <li class="cursor-pointer">Insert</li>
                <li class="cursor-pointer">Layout</li>
                <li class="cursor-pointer">Review</li>
                <li class="cursor-pointer">View</li>
            </ul>

            <div class="flex gap-3">
                <div class="cursor-pointer flex items-center gap-1 bg-white px-1 text-[#1C89FA]">
                    <span class="material-symbols-rounded text-lg">share_windows</span>
                    <p>Share</p>
                </div>

                <div class="hidden cursor-pointer lg:flex items-center gap-1 bg-white px-1 text-[#1C89FA]">
                    <span class="material-symbols-rounded text-lg">chat</span>
                    <p>Comments</p>
                </div>
            </div>
        </div>

        <div class="text-gray-800 flex items-center justify-between gap-3 p-1 lg:gap-5 bg-[#F4F4F4] shadow-md">
            <div>
                <span class="material-symbols-rounded text-lg">content_paste</span>
            </div>
            
            <div class="flex gap-1">
                <select class="outline-none w-full lg:p-1">
                    <option>Calibri</option>
                    <option>Arial</option>
                    <option>Inter</option>
                    <option>Montserrat</option>
                </select>
                <select class="outline-none lg:p-1">
                    <option>11</option>
                    <option>12</option>
                    <option>13</option>
                    <option>14</option>
                </select>
            </div>

            <div class="flex justify-between lg:gap-2">
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_bold</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_italic</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_underlined</span>
            </div>

            <div class="flex justify-between gap-1 lg:gap-2">
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_list_bulleted</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_list_numbered</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_underlined</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_indent_increase</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_indent_decrease</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_align_left</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_align_center</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_align_right</span>
                <span class="material-symbols-rounded text-xl lg:text-2xl">format_align_justify</span>
            </div>

            <div class="hidden md:flex gap-1">
                <select class="outline-none lg:p-1">
                    <option>Normal</option>
                    <option>Heading 1</option>
                    <option>Heading 2</option>
                    <option>Heading 3</option>
                </select>
                <select class="hidden xl:inline outline-none shrink lg:p-1">
                    <option>No spacing</option>
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                </select>
            </div>
        </div>
    </header>
</template>

<style scoped>
li.active-list {
    position: relative;
}

li.active-list::before {
    content: "";
    position: absolute;
    height: 3px;
    width: 100%;
    bottom: -5px;
}
</style>