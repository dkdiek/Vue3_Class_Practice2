<template>
  <!--리스트 렌더링 중첩 반복문-->

  <div>
    <!-- 방법 1-->
    <!-- cities 중 province가 경상도인 object를 js filter를 이용해서 반복 출력 v-for와 v-if를 엘리멘트에서 같이 사용 불가
    조건문에 해당 안되면 li자체가 생성x
    <ul>
      <li
        v-for="(city, index) in cities.filter((c) => c.province === '경상도')"
        :key="index"
      >
        {{ city.name }}
      </li>
    </ul> -->

    <!-- 방법2 -->
    <!--cities 중 province가 경상도인 object를 js filter를 이용해서 반복 출력 v-for와 v-if를 엘리멘트에서 같이 사용 불가
    조건문에 해당안되도 li는 생성되고 값만 화면에 출력안됨 marker는 화면에 노출된다
    
    <ul>
      <li v-for="(city, index) in cities" :key="index">
        <span v-if="city.province === '경상도'">{{ city.name }}</span>
      </li>
    </ul>-->

    <!-- 방법3 -->
    <!-- template을 만들어 v-for 껍데기 사용 -->
    <ul>
      <template v-for="(city, index) in cities" :key="index">
        <li v-if="city.province === '경상도'">
          {{ city.name }}
        </li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      cities: [
        { name: "서울", province: "경기도" },
        { name: "대전", province: "충청도" },
        { name: "대구", province: "경상도" },
        { name: "부산", province: "경상도" },
        { name: "인천", province: "전라도" },
        { name: "광주", province: "경기도" },
      ],
    };
  },
};
</script>

<style></style>
