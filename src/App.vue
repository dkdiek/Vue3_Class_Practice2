<template>
  <div>
    <h2>Hello Slot</h2>

    <!-- Slot을 사용하여 Hello slots를 보낼 수 있다
    <CardView> Hello Slots </CardView>
    <CardView>
      <img src="https://placimg.com/100/50/any" alt="random" />
    </CardView>
    <CardView>
      <ul>
        <li>짬뽕</li>
        <li>짜장</li>
      </ul>
    </CardView> -->
    <!-- camel케이스말고 아래처럼 써도 똑같다
    <card-view></card-view> -->

    <card-view>
      <!-- 지정한 slot이름을 v-slot으로 붙여주면 해당 slot에 들어간다 -->
      <template v-slot:header>
        <h3>Random image</h3>
      </template>
      <template v-slot:default>
        <img src="https://source.unsplash.com/random/100×100" alt="" />
      </template>
      <template v-slot:footer>
        <small>thank you</small>
      </template>
    </card-view>
  </div>
</template>

<script>
import CardView from "./components/slot/CardView.vue";
//
export default {
  name: "App",
  components: {
    CardView,
  },
  data() {
    return {};
  },
  //provide 정의 메소드 형태로 complevel3에서 값 바로 꺼낼 수 있도록
  provide() {
    return {
      name: this.username,
    };
  },
  //컴퓨티드 정의
  computed: {},
  //watch 정의
  watch: {},
  //디렉티브 정의
  directives: {},
  //메소드 정의
  methods: {},
};
</script>

<style></style>
