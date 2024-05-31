<template>
    <h3 class="border-b-2 border-[#bbb] mt-8 mb-4 py-2">Add new transaction</h3>
    <form @submit.prevent="onSubmit">
        <div>
            <label for="title" class="inline-block my-2">Title</label>
            <input type="text" id="title" placeholder="Enter title..." class="border border-[#dedede] rounded-sm p-2 w-full" v-model="title"/>
        </div>
        <div>
            <label for="amount" class="inline-block my-2">
                Amount <br/>
                <span class="text-neutral-400">(negative - expense, positive - income)</span>
            </label>
            <input type="text" id="amount" placeholder="Enter amount" class="border border-[#dedede] rounded-sm p-2 w-full" v-model="amount"/>
        </div>
        <button class="cursor-pointer bg-[#9c88ff] hover:bg-[#8272d6] shadow-lg text-white p-2 w-full my-4">Add transaction</button>
    </form>
</template>

<script setup>
    import { ref } from 'vue';
	import { toast } from "@steveyuowo/vue-hot-toast";

    const title = ref('');
    const amount = ref('');

    const emit = defineEmits(['transactionSubmitted'])
    
    const onSubmit = () => {
        if(!title.value) {
            toast.error('No title provided');
            return;
        }

        if(!parseFloat(amount.value.replace('$','').replace(',',''))) {
            toast.error('Invalid amount provided');
            return;
        }

        const transactionData = {
            title: title.value,
            amount: parseFloat(amount.value.replace('$','').replace(',',''))
        };

        emit('transactionSubmitted', transactionData);

        amount.value = '';
        title.value = '';
    }
</script>