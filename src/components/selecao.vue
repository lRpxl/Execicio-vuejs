<template>
  <div class="operation-select">
    <select @change="$emit('update:modelValue', $event.target.value)" :value="modelValue">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
  </div>
</template>

<script>
export default {
  props: ['modelValue'] // Usando v-model nativo
};
</script>

<style scoped>
.operation-select select {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
  width: 100%;
}
</style>
