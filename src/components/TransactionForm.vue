<template>
    <h3 class="border-b-2 border-[#bbb] mt-8 mb-4 py-2">Add new transaction</h3>
    <form>
        <div>
            <label for="title" class="inline-block my-2">Title</label>
            <input type="text" id="title" placeholder="Enter title..." class="border border-[#dedede] rounded-sm p-2 w-full"/>
        </div>
        <div>
            <label for="amount" class="inline-block my-2">
                Amount <br/>
                <span class="text-neutral-400">(negative - expense, positive - income)</span>
            </label>
            <input type="number" id="amount" placeholder="Enter amount" class="border border-[#dedede] rounded-sm p-2 w-full"/>
        </div>
        <button class="cursor-pointer bg-[#9c88ff] hover:bg-[#8272d6] shadow-lg text-white p-2 w-full my-4">Add transaction</button>
    </form>
</template>