<template>
  <div>
    <h2>Hello Component</h2>
    <button @click="displayDetail = true">show modal</button>
    <!-- 자식으로 부터 emit이벤트를 받을때 @로 받는다 closeDetail을 받으면 부모에서 정의한 close 메소드를 실행 -->
    <DetailView
      v-if="displayDetail"
      @closeDetail="close"
      @sendData="showData"
    />
  </div>
</template>

<script>
import DetailView from "./components/DetailView.vue";
//
export default {
  name: "App",
  components: {
    DetailView,
  },
  data() {
    return {
      displayDetail: false,
    };
  },
  //컴퓨티드 정의
  computed: {},
  //watch 정의
  watch: {},
  //디렉티브 정의
  directives: {},
  //메소드 정의
  methods: {
    close() {
      this.displayDetail = false;
    },
    showData(data) {
      console.log(data, "data sent");
    },
  },
};
</script>

<style></style>
