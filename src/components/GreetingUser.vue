<template>
  <div>
    <!-- 부모에서 넘겨준 none prop속성을 받을때 전체 감싸는 div태그가 있으면 적용되고 없으면 v-bind="$attrs"로 각 태그 적용 가능 -->
    <!-- String 받기 -->
    <h2 v-bind="$attrs">Hello user!! {{ username }}</h2>
    <!-- number 받기 -->
    <h3>오늘이 {{ numberOfVisit }} 번째 방문입니다.</h3>
    <!-- object 받기 -->
    <h3>사이트 이름은 {{ siteInfo.name }}입니다</h3>
  </div>
</template>

<script>
export default {
  name: "GreetingUser",
  // 부모에서 넘겨준 none porp 속성을 전체를 감싸는 div 태그에 적용을 자동으로 안시키고 $attrs로 붙인 것들만 적용되게
  inheritAttrs: false,
  props: {
    // 넘겨 받은 prop의 데이터 형식을 지정
    // 방법1) 바로 타입 설정
    // username: String,
    // 방법2) object 타입으로 데이터 형식과 default 값 지정 가능
    username: {
      type: String,
      default: "user",
    },
    numberOfVisit: {
      type: Number,
      default: 0,
    },
    siteInfo: {
      type: Object,
      //object는 return 형식으로 기본값 설정
      default: () => {
        return { name: "-", teacher: "-" };
      },
    },
  },
};
</script>

<style scoped></style>
