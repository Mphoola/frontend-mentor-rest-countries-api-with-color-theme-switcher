<template>
    <div class="rounded-md bg-white">
        <img :src="flag" :alt="alt">
        <div class="p-5">
            <h2 class="font-bold py-2">{{ country }}</h2>
            <p class="font-semibold">Population: <span class="text-gray-500">{{ population }}</span></p>
            <p class="font-semibold">Region: <span class="text-gray-500">{{ region }}</span></p>
            <p class="font-semibold">Capital: <span class="text-gray-500">{{ capital }}</span></p>
        </div>
    </div>
</template>
<script>
export default {
    name: "CountryCard",
    props: {
        alt: {
            type: String,
            required: false
        },
        flag: {
            type: String,
            required: true
        },
        country: {
            type: String,
            required: true
        },
        population: {
            type: String,
            required: true
        },
        region: {
            type: String,
            required: true
        },
        capital: {
            type: String,
            required: true
        }
    }
}
</script>