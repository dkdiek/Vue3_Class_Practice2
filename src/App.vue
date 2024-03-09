<template>
  <div>
    <h2>dynamic component</h2>
    <!-- 다이나믹 컴포넌트를 사용해 클릭할때 컴포넌트 이름을 적는다 -->
    <button @click="activeTab = 'MenuOne'">Menu1</button>
    <button @click="activeTab = 'MenuTwo'">Menu2</button>
    <button @click="activeTab = 'MenuThree'">Menu3</button>
    <!-- 컴포넌트 이름을 불러와 화면에 보인다 -->
    <!-- keep-alive를 사용하면 화면에 데이터가 유지된다 menu3에 입력창 값을 menu1 menu2에 갔다가 다시 돌아왔을때 날라가는 것을 방지 -->
    <keep-alive>
      <component :is="activeTab"></component>
    </keep-alive>
  </div>
</template>

<script>
import MenuOne from "./components/tabItems/MenuOne.vue";
import MenuTwo from "./components/tabItems/MenuTwo.vue";
import MenuThree from "./components/tabItems/MenuThree.vue";
//
export default {
  name: "App",
  components: {
    MenuOne,
    MenuTwo,
    MenuThree,
  },
  data() {
    return {
      username: "scalper",
      activeTab: "MenuOne",
    };
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
