<script setup>
defineProps({
    text: {
        type: String,
        default: 'Button'
    },
    state: {
        type: String,
        default: 'horror'
    },
    category: {
        type: Object,
        default(rawProps){
            return{
                action: 'border-b-red-500 hover:border-b-red-600',
                comedy: 'border-b-yellow-500 hover:border-b-yellow-600',
                horror: 'border-b-red-500 hover:border-b-red-600'
            }
        }
    },
    disabled:{
        type:Boolean,
        default: false
    }
})
const button = `w-full h-full border-2 border-[transparent]
                px-3 leading-3 hover:font-semibold rounded
                disabled:opacity-50 disabled:cursor-not-allowed`
</script>

<template>
    <button :class="[button, category[state]]"
            @click="$emit('change')" 
            :disabled="disabled"
            >{{ text }}</button>
</template>

<style>
    button{
        color: black;
    }
</style>