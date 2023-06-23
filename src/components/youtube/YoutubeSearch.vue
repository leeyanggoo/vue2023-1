<template>
  <div className="youtube__search">
    <input type="text" />
    <button>검색</button>
  </div>
</template>
<style lang="scss">
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
