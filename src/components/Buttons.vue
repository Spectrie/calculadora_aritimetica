<script setup>
    const props = defineProps({
        value:{
            type: String,
            required: true
        },
        onClick:{
            type: Function,
            required: true
        }
    });

    const handleClick = () => {
        props.onClick(props.value);
    };
</script>

<template>
    <button class="rounded-4" @click="handleClick">{{ value }}</button>
</template>

<style scoped>
    button{
        width: 100%;
        padding: 10px;
        font-size: 18px;
        background-color: rgb(77, 76, 76);
        color: #fff;
        border: none;
    }
    #operation{
    background-color: blue;
    }
</style>