<template>
  <div>
    <!--컴포넌트 불러오기3 username과 같이 prop으로 컴포넌트에 데이터를 넘겨 처리 !!!직접 값 넣지 말고 method등으로 보낼것
    :을 앞에 추가하면 data나 computed 쪽에서 선언된 데이터를 넘겨야함
    -->
    <GreetingUser
      :username="username"
      :numberOfVisit="numberOfVisit"
      :siteInfo="siteInfo"
    />

    <GreetingUser />
    <button @click="changeName()">변경</button>
  </div>
</template>

<script>
//컴포넌트 가져오기1
import GreetingUser from "./components/GreetingUser";
//
export default {
  name: "App",
  //컴포넌트 가져오기2
  components: {
    //GreetingUser: GreetingUser ES6에서 키와 밸류가 같으면 생략가능
    GreetingUser,
  },
  data() {
    return {
      username: "scalper",
      numberOfVisit: undefined,
      siteInfo: {
        name: "vue practice",
        teacher: "scalper",
        subject: "frontend",
      },
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
    changeName() {
      this.username = "DDOchi";
    },
  },
};
</script>

<style></style>
