<template>
     <div class="">
        <Navbar />

        <div class="px-6 pt-4">
            <router-link to="/">
                <div class="bg-white dark:text-white dark:bg-[#2B3743] dark:border-none border-2 px-6 py-1 flex space-x-2 items-center w-fit">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 dark:text-white">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18" />
                    </svg>
                    <span>Back</span>
                </div>
            </router-link>
            
            <div class="flex flex-col md:flex-row md:items-center mt-8 md:space-x-6">
                <img src="https://flagcdn.com/w320/mw.png" alt="">
                <div>
                    <h1 class="font-bold text-xl py-4 md:py-0 dark:text-white">Malawi</h1>

                    <div class="flex flex-col md:flex-row space-y-6 md:space-y-0 md:space-x-12">
                        <div>
                            <p class="font-semibold dark:text-white">Native Name: <span class="text-gray-500">Malawi</span></p>
                            <p class="font-semibold dark:text-white">Population: <span class="text-gray-500">102,290</span></p>
                            <p class="font-semibold dark:text-white">Region: <span class="text-gray-500">Africa</span></p>
                            <p class="font-semibold dark:text-white">Sub Region: <span class="text-gray-500">Southern Region</span></p>
                            <p class="font-semibold dark:text-white">Capital: <span class="text-gray-500">Lilongwe</span></p>
                        </div>
                        <div>
                            <p class="font-semibold dark:text-white">Top Level: <span class="text-gray-500">.mw</span></p>
                            <p class="font-semibold dark:text-white">Currencies: <span class="text-gray-500">Kwacha</span></p>
                            <p class="font-semibold dark:text-white">Language: <span class="text-gray-500">Chichewa, Tumbuka</span></p>
                        </div>
                    </div>

                    <div class="py-4 flex flex-col md:flex-row md:space-x-2">
                        <h1 class=" font-bold text-xl dark:text-white">Border Countries:</h1>
                        <div class="flex flex-wrap gap-2 pt-4 md:pt-0">
                            <div class="bg-white dark:bg-[#2B3743] dark:text-white dark:border-none border-2 px-6 py-1 items-center w-fit">
                               Mozambique
                            </div> 
                            <div class="bg-white dark:bg-[#2B3743] dark:text-white dark:border-none border-2 px-6 py-1 items-center w-fit">
                               Mozambique
                            </div> 
                            <div class="bg-white dark:bg-[#2B3743] dark:text-white dark:border-none border-2 px-6 py-1 items-center w-fit">
                               Mozambique
                            </div> 
                        </div>
                    </div>

                </div>
            </div>
        </div>
     </div>
</template>

<script>
import {useStore} from 'vuex'
import {onMounted, ref} from 'vue' 
import Navbar from '../components/Navbar.vue'
export default {
    name: 'Details',
    props: {
        name: {
            type: String,
            required: true
        }
    },
    components: {
        Navbar
    },
    setup(props) {
        const store = useStore();
        const country = ref({});

        onMounted(() => {
            store.dispatch('fetchCountry', props.name).then(() => {
                country.value = store.getters.getCountry
                console.log(country.value)
            })
        })

        return {
            country
        }
    }
}

</script>