<template>
    <div class="number-input">
        <input type="number" :value="value" @input="$emit('input', $event.target.value)" /><!-- Emite o valor para o componente pai -->
        
    </div>
</template>

<script>
export default {
    props: ['value']
};
</script>

<style scoped>
.number-input input {
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
    width: 100%;
    box-sizing: border-box;
    /*  Garante que o input ocupe o espaço correto */
}
</style>