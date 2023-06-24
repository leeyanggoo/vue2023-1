<template>
  <div class="youtube__tag">
    <div>
      <button
        v-for="(tag, index) in youtubeTags"
        :key="index"
        @click="btnClick(tag.name)"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["onSearch"],
  data() {
    return {
      youtubeTags: [
        { name: "react" },
        { name: "vue" },
        { name: "vite" },
        { name: "next.js" },
        { name: "javascript" },
        { name: "three.js" },
      ],
    };
  },
  methods: {
    btnClick(name) {
      this.onSearch(name);
    },
  },
};
</script>

<style lang="scss">
// youtube__tag
.youtube__tag {
  div {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    margin-top: 50px;

    button {
      border: 1px solid var(--button_red);
      padding: 10px 20px;
      margin: 0 10px;
      color: var(--button_red);
      cursor: pointer;
      background: linear-gradient(to right, var(--button_red) 50%, white 50%);
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
</style>
