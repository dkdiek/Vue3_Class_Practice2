<template>
  <div>
    <!-- id를 greeting으로 주면 GreetingUser 전체 div태그가 있으면 바로 div에 id가 적용되고
    전체를 감싸는 태그가 없으면 적용 안된다 또는 GreetingUser.vue에 태그에 v-bind="$attrs"를 쓰면 적용된다
     -->
    <GreetingUser id="greeting" />
  </div>
</template>

<script>
import GreetingUser from "./components/GreetingUser.vue";
//
export default {
  name: "App",
  components: {
    // ProductList,
    GreetingUser,
  },
  data() {
    return {
      // products: [
      //   { id: 0, name: "TV", price: 500000, company: "LG" },
      //   { id: 1, name: "전자레인지", price: 200000, company: "삼성" },
      //   { id: 2, name: "가스오븐", price: 300000, company: "한화" },
      //   { id: 3, name: "냉장고", price: 50000, company: "대우" },
      //   { id: 4, name: "에어컨", price: 100000, company: "해태" },
      // ],
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
