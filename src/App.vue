<template>
	<main class="flex flex-col items-center justify-center min-h-[100vh] m-0 font-lato bg-[#f7f7f7]">
		<Header class="w-72" />
		<div class="container max-w-72 m-7">
			<Balance />
			<RunningBalance class="my-4"/>
			<TransactionList></TransactionList>
		</div>
	</main>
</template>

<script>
	import Header from './components/Header.vue'
	import Balance from './components/Balance.vue'
	import RunningBalance from './components/RunningBalance.vue'
	import TransactionList from './components/TransactionList.vue'
	export default{
		components: {
			Header,
			Balance,
			RunningBalance,
			TransactionList
		},
	};
</script>