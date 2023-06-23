<template>
  <div className="youtube__tag">
    <ul>
      <li>
        <a href="/">코딩애플</a>
      </li>
      <li>
        <a href="/">리액트</a>
      </li>
      <li>
        <a href="/">Next.js</a>
      </li>
      <li>
        <a href="/">Javascript</a>
      </li>
      <li>
        <a href="/">프론트앤드</a>
      </li>
    </ul>
  </div>
</template>

<style lang="scss">
.youtube__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    margin-top: 50px;

    li {
      a {
        border: 1px solid var(--button_red);
        padding: 10px 20px;
        margin: 0 10px;
        color: var(--button_red);
      }
    }
  }
}
</style>
