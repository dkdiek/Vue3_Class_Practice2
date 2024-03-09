<template>
  <div>
    <!--if 조건에 따라 보여지고 안보여짐 false면 v-else가 출력됨 -->
    <h2 v-if="showName">My name is {{ user.name }}</h2>
    <h2 v-else>이름을 보여줄 수 없습니다.</h2>

    <!-- if문, else-if, else 중간에 다른 태그가 들어가면 안되고 이어져야 된다 -->
    <h2 v-if="user.age > 20">당신은 성인입니다.</h2>
    <h2 v-else-if="user.age > 14 && user.age < 20">청소년입니다.</h2>
    <h2 v-else>아이입니다.</h2>

    <!-- false일 때 v-if는 아예 렌더링을 안하고 v-show는 style을 none으로 설정 -->
    <h2 v-if="showName">{{ user.name }} IF</h2>
    <h2 v-show="showName">{{ user.name }} show</h2>

    <!--template으로 여러개 묶어서 조건 적용 - template은 html에 태그로 노출 안된다-->
    <ul>
      <template v-if="question === 'frontend'">
        <li>HTML은 재미있나요?</li>
        <li>css은 재미있나요?</li>
        <li>js는 재미있나요?</li>
      </template>
      <template v-else>
        <li>java는 재미있나요?</li>
        <li>python는 재미있나요?</li>
        <li>C#는 재미있나요?</li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      question: "frontend",
      showName: true,
      user: {
        name: "scalper",
        age: 1,
        job: "programmer",
      },
    };
  },
};
</script>

<style></style>
