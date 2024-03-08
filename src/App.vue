<template>
  <div>
    <h1>Hello</h1>
    <h1 id="title">Hello Title</h1>
    <!-- dyanamicId를 이용해서 id를 바꿔 css를 적용시킨다-->
    <h1 v-bind:id="dynamicId">Hello Title</h1>
  </div>
</template>
p
<script>
export default {
  name: "App",
  data() {
    return {
      dynamicId: "content",
    };
  },
};
</script>

<style>
#title {
  color: red;
}
#content {
  color: blue;
  background-color: pink;
}
</style>
