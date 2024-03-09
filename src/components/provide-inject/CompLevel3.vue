<template>
  <h2>component 3</h2>
  <h3>passed data from app.vue = {{ name }}</h3>
</template>

<script>
export default {
  name: "compLevel3",
  //app.vue에서 데이터 받기 complevel1,2 거치지 않고
  inject: ["name"],
};
</script>

<style></style>
