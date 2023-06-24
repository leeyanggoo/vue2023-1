<template>
  <div class="movie__tag container">
    <ul>
      <li>
        <router-link to="" @click="onClick('10749')">로맨스영화</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('28')">액션영화</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('35')">코미디영화</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('16')">애니메이션</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('27')">공포영화</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  methods: {
    onClick(value) {
      this.$emit("search", value);
    },
  },
};
</script>

<style lang="scss">
// movie__tag
.movie__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    margin-top: 50px;

    li {
      a {
        font-family: "GmarketSans";
        border: 1px solid var(--button_blue);
        padding: 10px 20px;
        margin: 0 10px;
        color: var(--button_blue);
        cursor: pointer;
        background: linear-gradient(
          to right,
          var(--button_blue) 50%,
          white 50%
        );
        background-size: 200% 100%;
        background-position: right bottom;
        transition: all 0.5s ease-out;
        &:hover {
          background-position: left bottom;
          color: #fff;
        }
      }
    }
  }
}
</style>
