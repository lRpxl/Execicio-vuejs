<template>
    <div class="number-input">
        <input type="number" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" />
    </div>
</template>

<script>
export default {
    props: ['modelValue']
};
</script>

<style scoped>
.number-input input {
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
    width: 100%;
    box-sizing: border-box;
    margin: 12px 0;
}
</style>