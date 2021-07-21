<template>
  <div class="img_inner mx-auto">
      <img class="img_resp" :src="src" :alt="name" width="640" height="640">
  </div>
</template>

<script>
export default {
   props: ["src", "name"],
}
</script>

<style>
.img_inner{
    width: 250px;
    height: 250px;
   
}

.img_resp{
    width: 100%;
    height:auto;
}
</style>