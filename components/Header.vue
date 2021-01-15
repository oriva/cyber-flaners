<template>
  <header class="header">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-auto">
          <a href="/" class="header__link">
            <div class="header__logo">
              <img src="/img/logo.png" alt="">
            </div>
            <RainbowTitle text="Cyber flaners"/>
          </a>
        </div>
        <div class="col">
          
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
  background-color: #000;
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
}
</style>
