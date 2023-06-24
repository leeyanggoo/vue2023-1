<template>
  <div class="unplash__tag container">
    <ul>
      <li>
        <router-link to="" @click="onClick('wallpapers')">배경화면</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('3d-renders')"
          >3D 렌더링</router-link
        >
      </li>
      <li>
        <router-link to="" @click="onClick('nature')">자연</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('animals')">동물</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('film')">필름</router-link>
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
// unplash__tag
.unplash__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    margin-top: 50px;

    li {
      a {
        font-family: "GmarketSans";
        border: 1px solid var(--button_green);
        padding: 10px 20px;
        margin: 0 10px;
        color: var(--button_green);
        cursor: pointer;
        background: linear-gradient(
          to right,
          var(--button_green) 50%,
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
