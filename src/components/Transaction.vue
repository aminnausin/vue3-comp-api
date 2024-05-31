<template>
    <li class="border-r-4 border-solid border-[#2ecc71] bg-white shadow-md text-[#333] flex justify-between relative p-3 my-3 group" :class="{ 'border-[#c0392b]': parseFloat(amount) < 0 }">
        {{ title }}<span>{{`${parseFloat(amount) < 0 ? '-$' : '$'}${Math.abs(parseFloat(amount))}`}}</span><DeleteButton @click="deleteTransaction(t_id)"/>
    </li>
</template>

<script setup>
    import DeleteButton from './DeleteButton.vue'
	const props = defineProps(['title', 'amount', 't_id'])

    const emit = defineEmits(['transactionDeleted']);

    const deleteTransaction = (id) => {
        emit('transactionDeleted', id);
    }
</script>