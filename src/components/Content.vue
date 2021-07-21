<template>
  <div class="text">
    <h2 class="name">{{ name }}</h2>
    <p class="desc">{{ desc }}</p>
    <span class="price">${{ price }}</span>
  </div>
</template>

<script>
export default {
  props: ["name", "desc", "price"],
};
</script>

<style>
.text {
  text-align: center;
}
.name {
  font-size: 22px;
}

.desc {
  font-size: 15px;
}

.price {
  font-size: 30px;
  font-weight: bold;
  color: #ea337c;
}
</style>