<template>
  <no-ssr>
    <full-page>
      <div class="section about" :class="{'loaded': isLoad}">
        <WhiteNoise :time="2"/>
        <div class="header-flaners">
          <div class="header-flaners__ed">
            <img src="/img/photo-flaners/ed.png" alt="">
          </div>
        </div>
      </div>
      <div class="section">
        <div class="container-fluid">
          <div class="row">
            <div class="col-3">
              <h2>Наши проекты</h2>
            </div>
            <div class="col-9">
              <div class="projects">
                <div class="project-item">
                  <img src="/img/my-game.jpg" alt="">
                </div>
                <div class="project-item">

                </div>
                <div class="project-item">

                </div>
                <div class="project-item">

                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </full-page>
  </no-ssr>
</template>

<script>
import WhiteNoise from '../components/animations/WhiteNoise.vue'

export default {
  components: {
    WhiteNoise,
  },
  layout: 'default',
  data() {
    return {
      isLoad: false,
    }
  },
  head() {
    return {
      title: 'кибер-фланеры стримы каждый день!',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Мы 4 стендап комика, застрявших в одной квартире в Москве в разгар пандемии. Отсутствие каких-либо выступлений и открытых микрофонов привело нас в онлайн. Разгоняем, играем в игры, импровизируем, готовим, пишем биты, фристайлим. Ждем когда снова можно будет проверять шутки на живой аудитории.'
        }
      ]
    }
  },
  mounted() {
    this.isLoad = true
  }
}
</script>

<style lang="scss">
@import "../assets/scss/bootstrap-grid.scss";
@import "../assets/scss/index.scss";

body {
  background-color: #000;
  color: #FFF;
}

.section {
  padding-top: 60px;
}

@keyframes flyEd {
  0% {
    bottom: 30%;
    left: -15%;
    transform: rotate(90deg);
  }
  75% {
    bottom: 30%;
    left: 30%;
    transform: rotate(90deg);
  }
  85% {
    bottom: 30%;
    left: 30%;
    transform: rotate(0);
  }
  100% {
    bottom: 0;
    left: 30%;
    transform: rotate(0);
  }
}
</style>

