<template>
  <div class="youtube__search container">
    <h2 class="blind">검색하기</h2>
    <input
      ref="inputRef"
      @keypress="onKeyPress"
      type="search"
      placeholder="보고 싶은 키워드를 검색하세요!"
    />
    <button type="submit" @click="onClick">검색하기</button>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$nextTick(() => {
      this.inputRef = this.$refs.inputRef;
    });
  },
  methods: {
    handleSearch() {
      const value = this.inputRef.value;
      this.onSearch(value);
    },
    onKeyPress(event) {
      if (event.key === "Enter") {
        this.handleSearch();
      }
    },
    onClick() {
      this.handleSearch();
    },
  },
  data() {
    return {
      inputRef: null,
    };
  },
  props: {
    onSearch: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style lang="scss">
// youtube__search
.youtube__search {
  text-align: center;
  margin-bottom: 50px;
  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    min-width: 300px;
    margin-right: 10px;
    border-radius: 50px;
  }
  button {
    @include button(#ff3344, #fff);
    // @include border(50px);
    border-radius: 50px;
  }
}
</style>
