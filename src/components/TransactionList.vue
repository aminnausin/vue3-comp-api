<template>
    <h3 class="border-b-2 border-[#bbb] mt-8 mb-4 py-2">History</h3>
    <ul id="list" class="list-none mb-10">
        <Transaction v-for="t in transactions" :key="t.id" :title="t.title" :amount="t.amount" :t_id="t.id" @transactionDeleted="handleDelete"></Transaction>
    </ul>
</template>

<script setup>
    import Transaction from './Transaction.vue'
	const props = defineProps({
        transactions: {
            type: Array,
            required: true,
        },
    });

    const emit = defineEmits(['transactionDeleted'])
    const handleDelete = (id) => {
        emit('transactionDeleted', id);
    }
</script>