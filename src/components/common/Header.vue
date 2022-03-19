<script setup>

</script>

<template>
  <header>
    <div class="header-container">
      <div class="logo">
        <img src="https://picsum.photos/159/39" alt="智遊科技" />
      </div>
      <div class="nav">
        <ul>
          <li>
            <a href="#">關於我們</a>
          </li>
          <li>
            <a href="#">服務系統</a>
          </li>
          <li>
            <a href="#">最新消息</a>
          </li>
          <li>
            <a href="#">常見問題</a>
          </li>
          <li>
            <a href="#">合作夥伴</a>
          </li>
          <li>
            <a href="#">聯絡我們</a>
          </li>
          <li class="lang">
            <select>
              <option value="tw">中文</option>
              <option value="en">English</option>
            </select>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
a {
  color: $gray;
  text-decoration: none;
}
.header-container {
  display: grid;
  grid-template-columns: 160px 1fr 2fr 77px;
  padding: 24px 0;
  height: 87px;
  .logo {
    grid-column: 2 / 3;
  }
  .nav {
    grid-column: -3 / -2;
    ul {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      height: 100%;
      li {
        align-self: center;
        text-align: center;
        padding: 0 10px;
      }
      a {
        display: block;
        padding: 5px 0;
      }
    }
  }
}
</style>