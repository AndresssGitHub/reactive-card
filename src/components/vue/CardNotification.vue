<script setup>
import { ref } from 'vue'

const counter = ref(0)

function decrement(){
    if(counter.value>0){
        counter.value--
    }
}

function increment(){
    counter.value++
}

</script>

<template>
    <div class="bg-slate-200 rounded py-8 px-6 w-96 shadow-md flex items-center flex-col">
        <div class="relative ">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTATOhCOrXw5nIxHGUVXxg8cEVd7Ny3WkRcDONjpYly095fxPJq4HaQRUyo0GKLDby1eFk&usqp=CAU"
                alt="James Rodriguez" title="J10" class="size-32 rounded-full">
            <div v-show="counter > 0" class="bg-blue-500 size-8  rounded-full text-white font-semibold flex items-center justify-center absolute top-0 right-0">
                {{ counter }}
            </div>
        </div>

        <p v-if="counter > 0" class="font-semibold animate-pulse text-yellow-500 mt-2">You have {{ counter }} new messages 😃</p>
        <p v-else class="text-gray-500 font-semibold mt-2 animate-pulse">Nobody writes to me 😢</p>

        <div class="flex justify-around  mt-4 w-32 items-center">
            <button @click="decrement" class="bg-red-500 px-4 py-1 rounded-lg font-bold text-lg text-white flex justify-center items-center w-10 hover:bg-red-600 transition-colors">-</button>
            {{ counter }}
            <button @click="increment" class="bg-green-500 px-4 py-1 rounded-lg font-bold text-lg text-white flex justify-center items-center w-10 hover:bg-green-600 transition-colors">+</button>
        </div>
    </div>
</template>