<template>
  <div>
    <h1>Hello</h1>
    <h1 id="title">Hello Title</h1>

    <!-- dyanamicId를 이용해서 id를 바꿔 css를 적용시킨다-->
    <h1 v-bind:id="dynamicId">Hello Title</h1>

    <!-- dyanamicId를 이용해서 data에 설정한 url로 이동시킨다-->
    <a v-bind:href="url">naver</a>

    <!-- object 사용해서 binding -->
    <img v-bind:src="image.src" v-bind:alt="image.alt" />
    <input v-bind:type="inputType" name="" id="" />
  </div>
</template>
p
<script>
export default {
  name: "App",
  data() {
    return {
      dynamicId: "content",
      url: "https://naver.com",
      image: {
        src: "https://placeimg.com/640/480/any",
        alt: "random image",
      },
      inputType: "color",
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
