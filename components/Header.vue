<template>
  <header class="header">
    <div class="container">
      <div class="row align-items-center justify-content-between">
        <div class="col-auto">
          <a href="/" class="header__link">
            <div class="header__logo">
              <img src="/img/logo.png" alt="">
            </div>
            <RainbowTitle text="Cyber flaners"/>
          </a>
        </div>
        <div class="col">
          <ul class="header__nav">
            <li>
              <a href="">О нас</a>
            </li>
            <li>
              <a href="">Наши проекты</a>
            </li>
          </ul>
        </div>
        <div class="col-auto">
          <a href="https://www.donationalerts.com/r/cybercomedians" target="_blank">Поддержать нас</a>

        </div>
      </div>
    </div>
  </header>
</template>

<script>
import RainbowTitle from './animations/RainbowTitle.vue'

export default {
  components: {
    RainbowTitle,
  },
}
</script>

<style lang="scss">
.header {
  position: fixed;
  z-index: 2;
  top: 0;
  left: 50%;
  display: flex;
  align-items: flex-end;
  justify-content: center;
  width: 100%;
  background-color: #2d2d2d;
  color: #fff;
  transform: translateX(-50%);
  cursor: pointer;
  vertical-align: bottom;
  transition: .3s;

  &:hover {
    padding: 5px 0;
  }

  &__link {
    display: flex;
    align-items: center;
    text-decoration: none;
  }

  &__logo {
    display: block;
    width: 4vw;

    img {
      display: block;
      width: 100%;
    }
  }

  &__nav {
    display: flex;
    align-items: center;
    flex-direction: row;
    padding-left: 0;
    margin-bottom: 0;
    list-style: none;
    li {
      margin-left: 15px;
      margin-right: 15px;
    }
    a {
      color: #bbb;
      transition-duration: .3s;
      transition-property: text-shadow,color;
    }
  }
}
</style>
