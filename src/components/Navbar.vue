<template>
    <div class="flex justify-between bg-white dark:bg-[#2B3743] px-6 py-4">
            <a href="" class="font-bold dark:text-white">Where in the world?</a>
            <div class="flex space-x-2 items-center">
                <svg xmlns="http://www.w3.org/2000/svg" @click="toggleDarkMode" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 cursor-pointer dark:text-white">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
                </svg>
                <div class="cursor-pointer dark:text-white" @click="toggleDarkMode">Dark Mode</div>

            </div>
        </div>
</template>

<script setup>
    const toggleDarkMode = () => {
        const html = document.querySelector('html')
        html.classList.toggle('dark')
    }
</script>