<template>
  <li>
    <p class="title">{{ product.name }}</p>
    <p class="image">
      <img
        :src="`https://placeimg.com/200/200/${product.id}`"
        :alt="product.name"
      />
    </p>
    <p class="price">{{ product.price }}</p>
  </li>
</template>

<script>
export default {
  name: "Product-item",
  props: {
    product: Object,
  },
};
</script>

<style scoped>
li {
  border: 2px solid salmon;
}
.title {
  font-size: 24px;
  color: #2c82c9;
  font-weight: bold;
}
</style>
