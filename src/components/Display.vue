<script setup>
const props = defineProps({
    displayValue: {
    type: String,
    required: true
}
});
</script>

<template>
    <input type="text" class="form-control text-end" :value="displayValue" disabled />
</template>

<style scoped>
input {
    font-size: 2rem;
    padding: 10px;
    text-align: right;
    width: 100%;
    color: black;
}
</style>