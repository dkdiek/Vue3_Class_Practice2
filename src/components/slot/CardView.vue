<template>
  <div class="card">
    <!-- APP.VUE에서 보낸 내용을 SLOT태그로 표시 -->
    <!-- 보낸 내용이 없을때 아래처럼 default를 써놓으면 적용된다  -->
    <!-- <slot>Default Value</slot> -->

    <!-- name안적으면 default -->
    <div class="card-header"><slot name="header"></slot></div>
    <div class="card-body"><slot name="default"></slot></div>
    <div class="card-footer"><slot name="footer"></slot></div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.3);
  padding: 1rem;
  margin-bottom: 1rem;
  width: 200px;
}
.card-header {
  color: red;
}
.card-body {
  color: pink;
}
.card-footer {
  color: green;
}
</style>
