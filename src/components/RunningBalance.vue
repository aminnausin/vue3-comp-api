<template>
    <div class="w-full shadow-md divide-x-2 divide-[#dedede] flex text-center bg-white">
        <div class="w-full my-4 flex items-center justify-center flex-col">
            <h4 class="text-md uppercase">
                Credits
            </h4>
            <p class="text-[#2ecc71]">{{`+$${Math.abs(parseFloat(credits))}`}}</p>
        </div>
        <div class="w-full my-4">
            <h4 class="text-md uppercase">
                Debits
            </h4>
            <p class="text-[#c0392b]">{{`-$${Math.abs(parseFloat(debits))}`}}</p>
        </div>
    </div>
</template>
<script setup>
    const props = defineProps(['credits', 'debits']);
</script>