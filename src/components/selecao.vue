<template>
  <div class="operation-select">
    <select @change="$emit('select-operation', $event.target.value)">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
  </div>
</template>

<script>
export default {
  props: ['value']
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
