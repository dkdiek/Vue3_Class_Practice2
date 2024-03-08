<template>
  <div>
    <!-- data 2가지를 배열로 담아 스타일 2개 적용 -->
    <h1 v-bind:style="[titleStyle, basicStyle]">Hello Title</h1>

    <!-- dyanamicId를 이용해서 id를 바꿔 css를 적용시킨다-->
    <h1 v-bind:id="dynamicId">Hello Title</h1>

    <!-- dyanamicId를 이용해서 data에 설정한 url로 이동시킨다-->
    <a v-bind:href="url">naver</a>

    <!-- object 사용해서 binding -->
    <img v-bind:src="image.src" v-bind:alt="image.alt" />
    <input v-bind:type="inputType" name="" id="" />

    <!-- data 이용해서 style 적용 -->
    <p v-bind:style="pStyle">Hello Vue!</p>
    <!-- inline style 적용 적용 -->
    <p v-bind:style="{ color: 'red', fontSize: `${basicSize}px` }">
      Hello Vue!
    </p>
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
      pStyle: "color: red;",
      basicSize: 50,
      basicStyle: {
        backgroundColor: "yellow",
      },
      titleStyle: {
        "font-weight": "bold",
        fontSize: "50px",
        border: "1px solid red",
      },
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
