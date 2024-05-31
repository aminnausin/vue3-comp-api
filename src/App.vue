<template>
	<main class="flex flex-col items-center justify-center min-h-[100vh] m-0 font-lato bg-[#f7f7f7]">
		<div class="container max-w-96">
			<Header class="mb-7"/>
			<Balance :total="total" />
			<RunningBalance class="my-4" :credits="credits" :debits="debits"/>
			<TransactionList :transactions="transactions"/>
			<TransactionForm/>
		</div>
	</main>
</template>

<script setup>
	import Header from './components/Header.vue'
	import Balance from './components/Balance.vue'
	import RunningBalance from './components/RunningBalance.vue'
	import TransactionList from './components/TransactionList.vue'
	import TransactionForm from './components/TransactionForm.vue'

	import { ref, computed } from 'vue';

	const transactions = ref([
        {id: 1, title: 'QR764 Flight Booking', amount: -906.67},
        {id: 2, title: 'Paprika and Garlic Powder', amount: -3.49},
        {id: 3, title: 'Tax Return', amount: 127.22},
        {id: 4, title: 'Rogers Repayment', amount: 35.96}
    ]);

	const total = computed(() => {
		return Math.round(parseFloat(transactions.value.reduce((sum, t) => sum + t.amount, 0 )) * 100) / 100;
	})

	const credits = computed(() => {
		return Math.round(parseFloat(transactions.value.reduce((sum, t) => {
			return t.amount >= 0 ? sum + t.amount : sum;
		}, 0 )) * 100) / 100;
	});

	const debits = computed(() => {
		return Math.round(parseFloat(transactions.value.reduce((sum, t) => {
			return t.amount < 0 ? sum + t.amount : sum;
		}, 0 )) * 100) / 100;
	})
</script>