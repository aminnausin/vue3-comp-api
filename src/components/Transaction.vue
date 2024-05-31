<template>
    <li class="border-r-4 border-solid border-[#2ecc71] bg-white shadow-md text-[#333] flex justify-between relative p-3 my-3 group">
        Cash on ground<span>$20</span><DeleteButton/>
    </li>
</template>

<script>
    import DeleteButton from './DeleteButton.vue'
	export default{
		components: {
			DeleteButton,
		},
	};
</script>