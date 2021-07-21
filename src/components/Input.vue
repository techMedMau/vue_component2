<template>
  <div>
    <span v-if="num > 0">
      <input type="button" value="-" class="minus" @click="$emit('decrease')"
    /></span>
    <span v-else><input type="button" value="-" class="minus" /></span>
    {{ num }}
    <span v-if="num < 5">
      <input type="button" value="+" class="plus" @click="$emit('increase')"
    /></span>
    <span v-else><input type="button" value="+" class="plus" /></span>
  </div>
</template>

<script>
export default {
  props: ["num"],
};
</script>

<style>
.plus,
.minus {
  border: 1px solid #ddd;
  border-radius: 3px;
  padding: 0.5rem 1rem;
  background-color: #fff;
  margin-bottom: 1rem;
}

.plus {
  margin-left: 3rem;
}
.minus {
  margin-right: 3rem;
}
</style>