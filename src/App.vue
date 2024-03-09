<template>
  <div>
    {{ user }}
    <!-- 영어는 바로바로 입력이 되지만 한글은 조합식 언어여서 한템포 느릴 수 있다 target사용하면 바로 반영되며 보일수 있음 -->
    <h1>{{ user.name }}</h1>
    <hr />
    <form>
      <div>
        <label for="name">이름</label>
        <!-- user의 name과 v-model로 연결 v-on을 @로 대체-->
        <input
          type="text"
          name=""
          id="name"
          v-model="user.name"
          @input="setValue"
        />
      </div>
      <div>
        <label for="age">나이</label>
        <!-- user의 name과 v-model로 연결 -->
        <input type="number" name="" id="age" v-model="user.age" />
      </div>
      <!--user에 city를 만들지 않았지만 v-model에 의해 선택된 city가 user에 생성된다-->
      <!--그래도 기초 값을 설정하는 게 좋음 문자나 null 등 어떤 타입이 들어올지 object에-->
      <div>
        <label for="city">사는 곳</label>
        <select name="" id="city" v-model="user.city">
          <option value="seoul">서울</option>
          <option value="daejeon">대전</option>
          <option value="daegu">대구</option>
          <option value="busan">부산</option>
          <option value="gwangju">광주</option>
        </select>
      </div>
      <!-- 멀티셀렉트 -->
      <div>
        <label for="favorite-food">좋아하는 음식</label>
        <select name="" id="favorite-food" multiple v-model="user.favorite">
          <option
            v-for="option in foodOptions"
            :value="option.code"
            :key="option.code"
          >
            {{ option.label }}
          </option>
        </select>
      </div>
      <!-- 체크박스 -->
      <!-- user에 job을 배열로 선언안해두면 선택해제가 모두 동시에 일어난다 -->
      <div>
        <label for="job">직업</label>
        프로그래머<input
          type="checkbox"
          name=""
          id=""
          value="programmer"
          v-model="user.job"
        />
        가수<input
          type="checkbox"
          name=""
          id=""
          value="singer"
          v-model="user.job"
        />
        선생님<input
          type="checkbox"
          name=""
          id=""
          value="teacher"
          v-model="user.job"
        />
      </div>
      <!-- radiobox -->
      <div>
        <label for="gender">성벌</label>
        남<input
          type="radio"
          name="gender"
          id=""
          value="male"
          v-model="user.gender"
        />
        여<input
          type="radio"
          name="gender"
          id=""
          value="female"
          v-model="user.gender"
        />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      foodOptions: [
        { label: "짜장면", code: "jj" },
        { label: "짬뽕", code: "jb" },
        { label: "탕수욕", code: "ts" },
      ],
      user: {
        name: "",
        age: 0,
        city: "서울",
        favorite: [],
        job: [],
      },
    };
  },
  //메소드 정의
  methods: {
    //한글 밀림없이 바로 보이도록
    setValue(e) {
      console.log(e.target.value);
      this.user.name = e.target.value;
    },
  },
};
</script>

<style>
label {
  font-size: 22px;
  font-weight: bold;
}
div {
  margin-bottom: 10px;
}
</style>
