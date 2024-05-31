<template>
    <h4 class="uppercase text-md">Current Balance</h4>
    <h1 id="balance" class="text-3xl">{{`${parseFloat(total) < 0 ? '-$' : '$'}${Math.abs(parseFloat(total))}`}}</h1>
</template>
<script setup>
    const props = defineProps(['total']);
</script>