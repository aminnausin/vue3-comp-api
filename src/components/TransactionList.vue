<template>
    <h3 class="border-b-2 border-[#bbb] mt-8 mb-4 py-2">History</h3>
    <ul id="list" class="list-none mb-10">
        <Transaction class="border-[#c0392b]">
        </Transaction>
        <Transaction class="border-[#2ecc71]">
        </Transaction>
    </ul>
</template>

<script>
    import Transaction from './Transaction.vue'
	export default{
		components: {
			Transaction,
		},
	};
</script>